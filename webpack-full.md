# Webpack

## install webpack

1. `npm init -y`
1. add `node_modules` to `.gitignore`
1. `npm install --save-dev webpack webpack-cli`
1. setup script in `package.json`
   ```js
     "scripts": {
     "start": "webpack"
   },
   ```
   nb: by default webpack will look for an `index.js` file inside of `src` folder  
   now, having provided an `index.js`, if we run `npm start` webpack will create a `bundle.js` inside a `dist` folder  
   add `<script src="./dist/main.js"></script>` to our index.html
1. add `dist` to `.gitignore`

## configure webpack

1. setup our `import` and `export` for all our files to indicate dependencies.  
   webpack makes sure everything loads in the correct order  
   remove all our additional script tags in index.html
1. create `webpack.config.js`  
   setup the entry and output files,a s well as dev mode to not minify our scripts by default
   ```js
   const path = require("path");
   module.exports = {
     mode: "development",
     entry: "./src/index.js",
     output: {
       filename: "main.js",
       path: path.resolve(__dirname, "dist")
     }
   };
   ```
   nb: use `devtool: "none",` for easier to read bundle.js files, it will get rid of the `eval` fn all over the place
1. change start script to:
   ```js
    "scripts": {
      "start": "webpack  --config webpack.config.js"
    },
   ```
1. rebuild with `npm start`

## Webpack loader for css

Webpack enables use of loaders to preprocess files. This allows you to bundle any static resource way beyond JavaScript. You can easily write your own loaders using Node.js.

We want Webpack to take care of our .css files without having to manually import them in our `index.html` one by one.

1. create a `main.js` at the root of our `app` folder
1. `npm install --save-dev css-loader style-loader`
1. add to webpack config
   ```js
   module: {
     rules: [
       {
         test: /\.css$/i,
         use: ["style-loader", "css-loader"]
       }
     ];
   }
   ```
   - `css-loader` turns our css into valid js code, and `style-loader` actually apply our style
   - `use` array loads in reverse order!
1. `import "./main.css";` in our `index.js` so that webpack knows about our css file.
1. rebuild with `npm start`

## change loader to sass & modifying bootstrap

1. `npm install --save-dev bootstrap` to get local copy of bootsrap & remove bootstrap cdn from our `index.html`
1. rename stylesheet to `main.scss` (simple example)

   ```scss
   $primary: teal;
   $danger: purple;
   @import "~bootstrap/scss/bootstrap";
   ```

1. `npm install sass-loader node-sass --save-dev`
1. change webpack config from css config to:
   ```js
     module: {
       rules: [
         {
           test: /\.s[ac]ss$/i,
           use: [
             // Creates `style` nodes from JS strings
             'style-loader',
             // Translates CSS into CommonJS
             'css-loader',
             // Compiles Sass to CSS
             'sass-loader',
           ],
         },
       ],
     },
   ```
1. `import "./main.scss";` in our `index.js` instead of the css
1. rebuild with `npm start`

## cache busting and HtmlWebpackPlugin

Prevent browsers from caching our assets when we don't want them to be cached

1. change output filename to:
   ```js
     output: {
       filename: "main.[contentHash].js",
       path: path.resolve(__dirname, "dist")
     },
   ```
   we'll generate a new file name every time we change something in our code.
1. we'll use a plugin to load the correct file in our `index.html`  
   `npm install --save-dev html-webpack-plugin`
1. change our webpack config to:

   ```js
   const path = require("path");
   var HtmlWebpackPlugin = require("html-webpack-plugin");

   module.exports = {
     mode: "development",
     entry: "./src/index.js",
     output: {
       filename: "main.[contentHash].js",
       path: path.resolve(__dirname, "dist")
     },
     plugins: [new HtmlWebpackPlugin()],
     module: {
       rules: [
         {
           test: /\.s[ac]ss$/i,
           use: [
             // Creates `style` nodes from JS strings
             "style-loader",
             // Translates CSS into CommonJS
             "css-loader",
             // Compiles Sass to CSS
             "sass-loader"
           ]
         }
       ]
     }
   };
   ```

1. rebuild with `npm start`  
   we get an `index.html` created in our `dist` folder  
   no content inside though, we need to supply a template to the plugin
1. - create our `template.html` in our `src` folder, it's the same as our `index.html` minus the script loaded at the end
   - in our webpack config, change the plugin to:
   ```js
     plugins: [
       new HtmlWebpackPlugin({
         template: "./src/template.html"
       })
     ],
   ```
1. rebuild with `npm start`  
   now it works and we get our site, except the images aren't loading
   we can remove the old `index.html`

## splitting dev and prod config

We want one _common_, one _dev_ and one _prod_ config file

1. `npm install --save-dev webpack-merge` to easily merge webpack config
1. change `package.json` scripts
   ```json
     "scripts": {
       "start": "webpack --config webpack.dev.js",
       "build": "webpack --config webpack.prod.js"
     },
   ```
1. `webpack.dev.js`

   ```js
   const path = require("path");
   const common = require("./webpack.common");
   const merge = require("webpack-merge");

   module.exports = merge(common, {
     mode: "development",
     output: {
       filename: "main.js",
       path: path.resolve(__dirname, "dist")
     }
   });
   ```

1. `webpack.prod.js`

   ```js
   const path = require("path");
   const common = require("./webpack.common");
   const merge = require("webpack-merge");

   module.exports = merge(common, {
     mode: "production",
     output: {
       filename: "main.[contentHash].js",
       path: path.resolve(__dirname, "dist")
     }
   });
   ```

1. `webpack.common.js`

   ```js
   const path = require("path");
   var HtmlWebpackPlugin = require("html-webpack-plugin");

   module.exports = {
     entry: "./src/index.js",
     plugins: [
       new HtmlWebpackPlugin({
         template: "./src/template.html"
       })
     ],
     module: {
       rules: [
         {
           test: /\.s[ac]ss$/i,
           use: [
             // Creates `style` nodes from JS strings
             "style-loader",
             // Translates CSS into CommonJS
             "css-loader",
             // Compiles Sass to CSS
             "sass-loader"
           ]
         }
       ]
     }
   };
   ```

1. start _dev_ with `npm start` and start _prod_ with `npm run build`  
   the _dev_ version sin't minimized and doens't uses content hashes

## add dev-server

1. `npm install --save-dev webpack-dev-server`
1. change `package.json` scripts
   ```json
    "scripts": {
      "start": "webpack-dev-server --config webpack.dev.js --open",
      "build": "webpack --config webpack.prod.js"
    },
   ```
1. `npm start` to run the dev build and open in on the browser; it will auto build on any changes; and you don't need a `dist` folder as the _dev-server_ does everything in memory  
   (`npm run build` to build the _prod_ version of our site)

## add html-loader, file-loader

let's fix images not loading because of path issues,
move `assets` folder to `src`

1. `html-loader` will `require` an image everytime it encounters one  
   `npm install --save-dev html-loader`
1. add to our common webpack rules:
   ```js
    {
      test: /\.html$/,
      use: ["html-loader"]
    }
   ```
   if we do `npm run build` it's going to fail because of our .svg and webpack doesn't know how to handle it  
   let's install file-loader to fix that
1. `npm install --save-dev file-loader`
1. add to our common webpack rules:
   ```js
    {
      test: /\.(svg|png|jpg|gif)$/,
      use: {
        loader: "file-loader",
        options: {
          name: "[name].[hash].[ext]",
          outputPath: "imgs"
        }
      }
    }
   ```
   add `esModule: false` as an option if there are issues with file paths

## add clean-webpack

we want to clean-up our dist folder from old files as we generate a new one everytime we build bacause of/thans to our use of hashes for cache-busting purpose

1. `npm install --save-dev clean-webpack-plugin`
1. change our `webpack.prod.js` to

   ```js
   const path = require("path");
   const common = require("./webpack.common");
   const merge = require("webpack-merge");
   const { CleanWebpackPlugin } = require("clean-webpack-plugin");

   module.exports = merge(common, {
     mode: "production",
     output: {
       filename: "main.[contentHash].js",
       path: path.resolve(__dirname, "dist")
     },
     plugins: [new CleanWebpackPlugin()]
   });
   ```

## Multiple entry points and vendor.js

We want to separate our own app code from vendor code (eg: bootstrap javascript), so we'd like two different bundles.js to be generated, one for our own code and one for vendor code.

We can do this with all vendor libraries we might use

1. create a `vendor.js` in our `src` folder
1. change entry in our `webpack.common.js` to

   ```js
   entry: {
     main: "./src/index.js",
     vendor: "./src/vendor.js"
   },
   ```

   change output in `webpack.prod.js` to

   ```js
    output: {
     filename: "[name].[contentHash].bundle.js",
     path: path.resolve(__dirname, "dist")
    },
   ```

   change output in `webpack.dev.js` to

   ```js
    output: {
     filename: "[name].js",
     path: path.resolve(__dirname, "dist")
    },
   ```

1. in `vendor.js`:

   ```js
   import "bootstrap";
   ```

   add a navbar in our `template.html` (it requires js to work) to show it working

1. if we run `npm start` we run into issues as bootstrap need popper and jquery to run, let's install those  
   `npm install --save-dev jquery popper.js`  
   now `npm start` ill work and our bootstrap navbar will be functional

## Extract css

nice to have a separate css file in production rather than wait for javascript to inject for performance reasons
we (and our users) don't want to have to wait for js to load before loading css into our site

1. `npm install --save-dev mini-css-extract-plugin`
1. add to our `webpack.prod.js`

   ```js
   const MiniCssExtractPlugin = require("mini-css-extract-plugin");

   plugins: [
     new MiniCssExtractPlugin({ filename: "[name].[contentHash].css" }),
     new CleanWebpackPlugin()
   ];
   ```

1. remove the sass rules from `webpack.common.js` and add it to `webpack.dev.js`
   ```js
   module: {
     rules: [
       {
         test: /\.s[ac]ss$/i,
         use: [
           // Creates `style` nodes from JS strings
           "style-loader",
           // Translates CSS into CommonJS
           "css-loader",
           // Compiles Sass to CSS
           "sass-loader"
         ]
       }
     ];
   }
   ```
1. add rule to `webpack.prod.js`
   ```js
   module: {
     rules: [
       {
         test: /\.s[ac]ss$/i,
         use: [
           // extract css into files
           MiniCssExtractPlugin.loader,
           // Translates CSS into CommonJS
           "css-loader",
           // Compiles Sass to CSS
           "sass-loader"
         ]
       }
     ];
   }
   ```

## Minify JS, CSS, and HTML in prod

1. `npm install --save-dev optimize-css-assets-webpack-plugin`
1. nb: we'll need to add `terser` back in for js minimization; and we'll use html-webpack-plugin (already installed) to minify our html
1. add to our `webpack.prod.js`

   ```js
   const OptimizeCssAssetsPlugin = require("optimize-css-assets-webpack-plugin");
   const TerserPlugin = require("terser-webpack-plugin");
   const HtmlWebpackPlugin = require("html-webpack-plugin");

   optimization: {
     minimizer: [
       new OptimizeCssAssetsPlugin(),
       new TerserPlugin(),
       new HtmlWebpackPlugin({
         template: "./src/template.html",
         minify: {
           removeAttributeQuotes: true,
           collapseWhitespace: true,
           removeComments: true
         }
       })
     ]
   },
   ```
