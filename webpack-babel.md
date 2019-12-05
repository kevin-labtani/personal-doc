# install babel

1. `npm init -y`
2. `npm install --save-dev @babel/core @babel/cli`
3. usage:  
   use `npx babel script.js` to output to stdout  
   use `npx babel script.js --out-file script-compiled.js` to output to a file  
   npx `babel script.js --watch --out-file script-compiled.`js to watch and compile
4. create config to have babel actually do something `npm install @babel/preset-env --save-dev`  
    create `.babelrc` and add
   ```JS
   {
   "presets": ["@babel/preset-env"]
   }
   ```
5. add the build script to package.json : `"build": "babel src/index.js --out-file public/scripts/index.js --preset env --watch"`  
   run `npm run build` to watch and compile our `input.js` file.
6. when distributing, remove node_modules and tell ppl to use `npm install`

# install webpack

7. `npm install webpack webpack-cli --save-dev`
8. add `webpack": "webpack"` to build scripts in package.json
9. setup `webpack.config.js` in root and add

   ```JS
   const path = require("path");

   module.exports = {
     entry: "./src/index.js",
     output: {
       filename: "bundle.js",
       path: path.resolve(__dirname, "public/scripts")
     }
   };
   ```

10. `npm run webpack`

# add babel into webpack

11. `npm install --save-dev babel-loader`
12. add to `webpack.config.js`:
    ```JS
    module: {
      rules: [
        {
          test: /\.js$/,
          exclude: /node_modules/,
          use: {
            loader: "babel-loader",
            options: {
              presets: ["@babel/preset-env"]
            }
          }
        }
      ]
    }
    ```
13. remove build script (specific to babel) from package.json as we no longer need it  
    `"build": "babel src/index.js --out-file public/scripts/index.js --preset env --watch",`

# automate

14. change the script from `"webpack": "webpack"` to `"webpack": "webpack --watch"`

or

14. use webpack-dev-server:

    1. `npm install webpack-dev-server --save-dev`
    1. add to `webpack.config.js`:

       ```js
       devServer: {
       contentBase: path.join(__dirname, "public"),
       publicPath: "/scripts/",
       compress: true,
       port: 9000
       }
       ```

    1. add `"dev-server": "webpack-dev-server"` to scripts (and remove all others)
    1. run with `npm run dev-server`

# setup dev and prod

15. final scripts for `package.json`:
    ```js
      "scripts": {
        "dev-server": "webpack-dev-server --mode development",
        "build": "webpack --mode production"
      },
    ```
    use `npm run dev-server` tor dev, `npm run build` to build
16. add source map so that the browser can map the compiled code back to the original code to make it easier for us to work with the browser dev tools, as otherwise we get the babel compiled code there and not our original code, with:  
    add `devtool: "source-map"` to `webpack.config.js`

# polyfills

17. `npm install --save-dev @babel/polyfill`
18. `entry: ["@babel/polyfill", "./src/index.js"],` in `webpack.config.js`

# dealing with multiple HTML files

19. use multiple `bundles.js` in `webpack.config.js`
    ```js
    entry: {
      index: ["@babel/polyfill", "./src/index.js"],
      edit: ["@babel/polyfill", "./src/edit.js"]
    },
    output: {
      path: path.resolve(__dirname, "public/scripts"),
      filename: "[name]-bundle.js"
    },
    ```

# fix huge file size

20. add `"browserslist": "> 0.25%, not dead",` to `package.json`
21. change babel presets in `webpack.config.js` to
    ```js
    presets: [
      [
        "@babel/preset-env",
        {
          useBuiltIns: "usage",
          debug: true
        }
      ]
    ];
    ```
    nb: `.babelrc` isn't really needed if we put the babel config in Webpack, if we use both, the Webpack configuration will overwrite the options in .babelrc
22. change entry in `webpack.config.js` back to
    ```js
    entry: {
      index: "./src/index.js",
      edit: "./src/edit.js"
    },
    ```

# Updating to Babel 7.4

23. run `npm install core-js@3 --save`
24. change babel presets in `webpack.config.js` to
    ```js
    presets: [
      [
        "@babel/preset-env",
        {
          useBuiltIns: "usage",
          corejs: 3,
          debug: true
        }
      ]
    ];
    ```
25. run `npm uninstall @babel/polyfill` as it's no longer necessary

# fix Can't resolve 'regenerator-runtime/runtime'

26. `npm install --save-dev @babel/plugin-transform-runtime`
27. `npm install --save @babel/runtime`
