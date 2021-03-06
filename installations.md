# Install Your Development Environment

## Operating System ([source](https://www.theodinproject.com/courses/web-development-101/lessons/prerequisites))

We use Ubuntu or Xubuntu in a VM

### Installing Xubuntu in a VM on Windows

1.  Download [VirtualBox](https://www.virtualbox.org/wiki/Downloads) for Windows hosts.
1.  Download the latest LTS release from [Xubuntu](https://xubuntu.org/download)
1.  Install VirtualBox
1.  Set up Xubuntu  
     Click on the “New” button to create a virtual operating system. Give it a name of “Xubuntu”, leave the “Machine Folder” as is, set the “Type” to “Linux” and be sure “Version” is set to “Ubuntu (64-bit)”. Continue by pressing “Next”, and choose the following options in the next steps:

            1. Memory size: Use 2048 MB or more if possible.
            2. Hard disk: “Create a virtual hard disk”.
            3. Hard disk file type: Choose the VDI (VirtualBox disk image) option.
            4. Storage on physical hard disk: “Dynamically allocated”.
            5. File location and size: 20 GB for the virtual hard disk or more is recommended.

    After completing the last step, click the “Create” button. Your new virtual OS should now appear in the menu. Right click on it, and go to “Settings”. Click on the “System” tab and then the “Processor” tab. Increase the Processor(s) to 2. If this screen prevents you from increasing processors, you need to [enable virtualization](https://www.google.com/search?q=enable+virtualization+windows) in your computer’s BIOS/UEFI settings.  
    Next, go to the “Storage” tab and in the “Attributes” column, beside the “Optical Drive” indicator, click the round, blue icon. This will present a drop-down menu. Click “Choose Virtual Optical Disk File…” and select the Xubuntu ISO file you downloaded earlier. If you aren’t sure where to find it, start by looking in your Downloads folder.  
    With all that complete, click “OK” to save the changes.  
    You can start the VM by right clicking on the icon in the menu and by clicking the large “Start” arrow at the top.  
    When the VM starts up, you’ll be asked to install Xubuntu. All of the default options can be left alone, including the Installation type (“Erase disk and install Ubuntu”).

1.  Install and enable Guest Additions  
    With the vm running, do the following steps:

    1. Click “Devices” -> “Insert Guest additions CD image” in the menu bar
    1. Open a terminal by pushing `ctrl + alt+ t` on the keyboard, if a terminal does not open, click anywhere on the desktop of the VM and try again.
    1. Type the following command into the terminal: `sudo apt install gcc make perl` You will be asked to type in the password you setup earlier. As you type your password, you’ll notice there is no visual feedback. This is a security measure. Trust that it is taking you input. (Just type it and then push enter). If an error is thrown, reboot the VM and try the steps in this list again.
    1. Run: `sudo /media/$USER/VBox*/VBoxLinux*.run` This may ask you for a password as well.
    1. Run `reboot` in the terminal, and the VM should reboot. If this does not work, reboot the VM by clicking the “start” menu, and selecting “reboot.”
    1. Click **devices** in the menu bar and go to **shared clipboard** then select the bidirectional option.

## Visual Studio Code

### Installing visual studio code

Install VS Code from the .deb on [the site](https://code.visualstudio.com/)

### Set up

1. Turn Word Wrap on
1. Install [Fira Code](https://github.com/tonsky/FiraCode/wiki/Installing) font and turn on font ligatures
1. Automatically format pasted code `"editor.formatOnPaste": true`
1. Highlight modified tabs `"workbench.editor.highlightModifiedTabs": true`
1. Autosave `"files.autoSave": "afterDelay"`
1. Enable font ligatures `"editor.fontLigatures": true`
1. (optional) Change tab size to 2 spaces
1. emmet config:
   ```json
     "emmet.includeLanguages": {
       "javascript": "javascriptreact",
       "php": "html"
     }
   ```
1. Install **Solarized Color Theme** extension
1. Install **Material Theme** and **Material Icon Theme**
1. Install **Live Server extension**  
   open a html file and then right-click and choose _open with live server_
1. Install **HTML CSS Support** for Class and Id attribute completion
1. Install **Auto Rename Tag** for auto renaming of the paired tag when you rename one of them
1. Install **Prettier - Code formatter**  
   change settings > _format on save_ to enable
1. Install **Formatting Toggle** to be able to toggle on or off the formatter
1. Install **ESLint** for JS linting
1. Install **indent-rainbow** for easier to see indentations
1. Install **Bracket Pair Colorizer 2** for colorized brackets pair
1. Install **Code Spell Checker** to help catch common spelling errors in code nb: check for English
1. Remote style sheets can be specified in VS Code settings:
   ```json
   "css.remoteStyleSheets": [
   "https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.6/css/bootstrap.min.css"
   ]
   ```
1. Install **Babel es6/es7** extension for JS
1. Install **CSS Peek** extension, use F12 to go to css rule when on the html doc
1. Install **Polacode** extension for code screenshots
1. Install **ES7 React/Redux/GraphQL/React-Native snippets** for react snippets

### Basic commands

- Multiple cursor with `ctrl + click`, do it again on a specific cursor to remove it
- Multiple cursors for next occurrence with `ctrl + d` and for all occurrences with `ctrl + shift + l`
- `alt + shift + click and drag` to drag a bunch or cursors across lines
- `alt + shift + down or up arrow` to add cursor above or below
- Basic navigation `ctrl + home` to go to the beginning of the document, `ctrl + end` to go to the end  
   `home` to go to the beginning of a line, `end` to go to to the end
- Get into a line and use `alt + up or down` to move the line around the document
- Get into a line and use `ctrl + c` to copy the line and then `ctrl + v` to paste it
- `ctrl + shift + k` to delete a line
- `ctrl + shift + alt + down or up arrow` to copy line down or up
- `ctrl + /` to add a comment, select text and then do `ctrl + /` to comment out a block, do it again to undo the comment
- `ctrl + shit + v` to open a live preview for a .md file
- `ctrl + p` to go to file
- click on a variable and press `F2` to rename all instances

## Git and Github

### Installing Git

1. Update the packages  
   `sudo apt-get update`  
   `sudo apt-get upgrade`
2. Install git  
   `sudo apt-get install git`

### Configuring Git

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
git config --global credential.helper 'cache --timeout=3600'
git config --global push.default current
```

Last one pushes the current branch to a branch of the same name
After this, do `git push -u` (for `git push --set-upstream`) and it'll automatically push the current local branch to a remote branch of the same name, set up tracking and create it if it doesn't exist.

[Add a new SSH key to your GitHub account](https://help.github.com/en/articles/adding-a-new-ssh-key-to-your-github-account)  
[Testing your SSH connection](https://help.github.com/en/articles/testing-your-ssh-connection)

Then move on to [Using Git](/git.md)

## Terminal ([Source](https://wesbos.com/command-line-video-tutorials/))

`ctrl + shift + t` to start the terminal  
`ctrl + shift + c` to copy in the terminal  
`ctrl + shift + v` to paste in the terminal  
`tab` completion is a thing!

### Basic Commands

| Command                   | What it does                                                                                             |
| ------------------------- | -------------------------------------------------------------------------------------------------------- |
| `pwd`                     | for present working directory, to find out where we are                                                  |
| `cd name-of-dir`          | to change to _name-of-dir_ directory                                                                     |
| `cd ..`                   | to go up a level in directories                                                                          |
| `cd ~`                    | to go to the home directory                                                                              |
| `mkdir`                   | to make a directory                                                                                      |
| `ls`                      | to list the files in the directory                                                                       |
| `ls -l`                   | same but with ownership and group information                                                            |
| `rm name-of-file`         | to remove _name-of-file_                                                                                 |
| `rm -r name-of-directory` | to remove _name-of-dir_                                                                                  |
| `touch name-of-file.txt`  | to create _name-of-file.txt_                                                                             |
| `cp a.txt b.txt`          | to copy _a.txt_ to _b.txt_                                                                               |
| `mv a.txt b.txt`          | to rename _a.txt_ to _b.txt_                                                                             |
| `clear`                   | to clear the terminal window                                                                             |
| ------------              | ------------                                                                                             |
| `man`                     | to display an interface to the on-line reference manuals                                                 |
| `whoami`                  | to print current logged user                                                                             |
| `whatis`                  | to display one-line manual page descriptions                                                             |
| `echo "42" > first.txt`   | to write _"42"_ to the (existing) _first.txt_ file                                                       |
| `chown vivek demo.txt`    | to change file ownership to _vivek_ user                                                                 |
| `chmod`                   | to change permissions of a file; [guide](https://www.pluralsight.com/blog/it-ops/linux-file-permissions) |
| 'ps -aux \| less'         | to report a snapshot of the current processes.                                                           |

### Install `vim`

Run through `vimtutor`

### Installing ZSH and Oh My Zsh

Z-shell is one of the most popular shell  
[Oh My Zsh](https://ohmyz.sh/) is a framework buit on top of ZSH

1. Install prerequisites  
   `sudo apt install zsh`  
   `sudo apt-get install powerline fonts-powerline`  
   `echo "\ue0b0 \u00b1 \ue0a0 \u27a6 \u2718 \u26a1 \u2699".` to see if your font is compatible
1. Install oh-my-zsh  
   `sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`  
   It should prompt you to change the default shell to oh-my-zsh
1. Log out and Log back in

### Customize Terminal colors and font

- You can change the colors and font through the terminal configuration
- Pick Solarized dark
- Install Powerline fonts
  ```
  $ git clone https://github.com/powerline/fonts.git
  $ cd fonts
  $ ./install.sh
  ```

### Customize Oh My Zsh theme and prompt

Check out Oh my zsh [github](https://github.com/robbyrussell/oh-my-zsh) to see existing themes  
`code ~/.zshrc` to edit, then change `ZSH_THEME` env variable to the chosen theme, eg. [`ZSH_THEME="agnoster"`](https://github.com/agnoster/agnoster-zsh-theme)  
restart the terminal to apply the theme

### Zsh basic features

- Able to use lowercase even if dir or file name is uppercase, it's smart enough to change
- `cd + space + tab` will open a list of all directories (with already escaped spaces), `tab` again and you can navigate through the list with arrow keys
- Use `~` to go home, or `..` to go up a level without having to type `cd`
- `ctrl` and click a link will take you to it
- Use `take name_of_dir` to replace `mkdir name_of_dir` + `cd name_of_dir`
- Use eg. `ls - tab` to see all the possible flags for ls

### Zsh advanced hisory

Type the command eg. `git + space` and then use up/down arrow to navigate through your history for that specific command

### Zsh plugins

See [plugins](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins) for a list  
`code ~/.zshrc` to add a plugin to the plugin list eg. **extract**  
`source ~/.zshrc` to update  
Now you can extract any file with `extract abc.tar.gz` and don't have to memorize the specifics  
`git` plugin is installed by default, use `git + space + tab` to see all the possible commands for git

### Configure Zsh for use in vscode terminal

- install font

```
git clone https://github.com/abertsch/Menlo-for-Powerline.git
sudo mv "Menlo for Powerline.ttf" /usr/share/fonts/
sudo fc-cache -vf /usr/share/fonts/
```

- settings:

```json
"terminal.external.linuxExec": "/usr/bin/zsh",
"terminal.integrated.shell.linux": "/usr/bin/zsh",
"terminal.integrated.fontFamily": "Menlo for Powerline",
```

## Update Nodejs to v10.x

install an use `n` to update the node.js shipped with ubuntu

```
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
```

or use the following and run as `nodejs`

```
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## Install nvm and node

as an alternative to previous point

1. `cd ~/` from anywhere then `git clone https://github.com/nvm-sh/nvm.git`

2. `cd ~/.nvm` and check out the latest version with `git checkout v0.36.0`
3. activate nvm by sourcing it from your shell: `. nvm.sh`

edit `~./zshrc`, adding the following snippet to the end:

```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

then install the latest lts version of node with `nvm install --lts`

## XAMPP (PHP, Apache & MySQL)

1. download [XAMPP](https://www.apachefriends.org/index.html)
1. `sudo apt install net-tools`
1. install with `chmod 755 xampp-linux-*-installer.run` and `sudo ./xampp-linux-*-installer.run`
1. start XAMPP with `sudo /opt/lampp/lampp start`  
   or use gui with `cd /opt/lampp` and `sudo ./manager-linux-x64.run`
1. stop XAMPP with `sudo /opt/lampp/lampp stop`
1. install php `sudo apt-get install php`
1. configure VSCode
   1. add **PHP IntelliSense** to VSCode
   1. add **PHP CS Fixer** to VSCode
   1. add to `settings.json`
      ```json
        "[php]": {
        "editor.defaultFormatter": "junstyle.php-cs-fixer",
        },
        "php.suggest.basic": false,
        "php-cs-fixer.rules": "@PhpCsFixer",
      ```

nb:

- if we get the error "Another web server is already running" when starting xampp do:
  `sudo netstat -nap | grep :80`
  You’ll see apache2 and there is 3–4 digit numbers before it, so do
  `sudo kill [number]`

- run `sudo chown -R $USER:$USER .` in folders inside htdocs if we get permissions issues  
  ` sudo chmod 777 -R /opt/lampp/htdocs` will make the file readable, writable and executable by everyone

## Prettier and ESLint with airbnb rules

1. `npm install --save-dev prettier`
1. `npm install --save-dev eslint`
1. install Prettier and ESLint as VS Code extension
1. `npm init -y` in local project
1. make a prettier config file `touch .prettierrc`

   ```json
   {
     "semi": true,
     "trailingComma": "all",
     "singleQuote": false,
     "printWidth": 80,
     "tabWidth": 2
   }
   ```

1. `npm install --save-dev eslint-config-prettier eslint-plugin-prettier`
1. make an eslint config `touch .eslintrc.json`

   ```json
   {
     "extends": ["prettier"],
     "plugins": ["prettier"],
     "rules": {
       "prettier/prettier": ["error"]
     }
   }
   ```

1. create an ignore file for files you want to ignore `.eslintignore`
1. `npx install-peerdeps --dev eslint-config-airbnb`  
    change `.eslintrc.json` to

   ```json
   {
     "env": {
       "browser": true,
       "es6": true,
       "node": true
     },
     "extends": ["airbnb", "prettier"],
     "plugins": ["prettier"],
     "rules": {
       "prettier/prettier": ["error"]
     }
   }
   ```

1. running `npx eslint --init` also an option to setup eslint

## Install and run MongoDB

1. follow install [instructions](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)
1. start MongoDB with `sudo service mongod start`
1. verify that MongoDB has started with with `sudo service mongod status`
1. stop MongoDB with `sudo service mongod stop`
1. restart MongoDB with `sudo service mongod restart`
1. install `robo3t` gui following [instructions](https://askubuntu.com/questions/739297/how-to-install-robomongo-on-ubuntu/781793), then run it with `robo3t`

## Deploy to Heroku 101

1. `heroku login`
1. `heroku create name-of-app` nb: setup heroku remote
1. to add key-value env variable `heroku config:set key=value`
1. `git push heroku master`
1. to push a subfolder: `git subtree push --prefix name-of-folder heroku master`
