04 JUIN 2020

```json
{
  "editor.wordWrap": "on",
  "workbench.colorTheme": "Community Material Theme Ocean",
  "editor.formatOnSave": true,
  "liveServer.settings.donotShowInfoMsg": true,
  "editor.multiCursorModifier": "ctrlCmd",
  "window.zoomLevel": 0,
  "editor.tabSize": 2,
  "editor.tabCompletion": "on",
  "diffEditor.ignoreTrimWhitespace": false,
  "explorer.confirmDragAndDrop": false,
  "workbench.editor.highlightModifiedTabs": true,
  "files.autoSave": "afterDelay",
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true,
  "terminal.external.linuxExec": "/usr/bin/zsh",
  "terminal.integrated.shell.linux": "/usr/bin/zsh",
  "terminal.integrated.fontFamily": "Menlo for Powerline",
  "terminal.integrated.fontSize": 12,
  "terminal.integrated.rendererType": "dom",
  "workbench.iconTheme": "eq-material-theme-icons-ocean",
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[php]": {
    "editor.defaultFormatter": "junstyle.php-cs-fixer"
  },
  "editor.minimap.enabled": false,
  "breadcrumbs.enabled": true,
  "editor.formatOnPaste": true,
  "editor.formatOnType": true,
  "html.format.wrapLineLength": 80,
  "editor.formatOnSaveTimeout": 5000,
  "php.suggest.basic": false,
  "php-cs-fixer.rules": "@PhpCsFixer",
  "php-cs-fixer.executablePath": "${extensionPath}/php-cs-fixer.phar",
  "php-cs-fixer.lastDownload": 1588674891581,
  "php-cs-fixer.onsave": true,
  "eslint.alwaysShowStatus": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "php": "html"
  },
  "files.watcherExclude": {
    "**/.git/objects/**": true,
    "**/.git/subtree-cache/**": true,
    "**/node_modules/*/**": true
  },
  "javascript.updateImportsOnFileMove.enabled": "always",
  "explorer.confirmDelete": false,
  "dart.flutterSdkPath": "/home/user/Desktop/Flutter/flutter",
  "workbench.colorCustomizations": {},
  "editor.semanticHighlighting.enabled": false
}
```

25 AUG 2020 WSL2 env

```json
{
  "terminal.integrated.shell.windows": "C:\\WINDOWS\\System32\\wsl.exe",
  "terminal.integrated.fontFamily": "Fira Code, Menlo for Powerline",
  "editor.fontFamily": "Fira Code, Consolas, 'Courier New', monospace",
  "workbench.colorTheme": "Community Material Theme Palenight",
  "workbench.editor.highlightModifiedTabs": true,
  "files.autoSave": "afterDelay",
  "editor.fontLigatures": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "php": "html"
  },
  "workbench.iconTheme": "material-icon-theme",
  "editor.wordWrap": "on",
  "window.zoomLevel": 0,
  "editor.tabSize": 2,
  "editor.tabCompletion": "on",
  "diffEditor.ignoreTrimWhitespace": false,
  "explorer.confirmDragAndDrop": false,
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "editor.minimap.enabled": false,
  "liveServer.settings.donotShowInfoMsg": true,
  "breadcrumbs.enabled": true,
  "editor.formatOnSave": true,

  "editor.formatOnPaste": true,
  "editor.formatOnType": true,
  "html.format.wrapLineLength": 80,
  "eslint.alwaysShowStatus": true,
  "files.watcherExclude": {
    "**/.git/objects/**": true,
    "**/.git/subtree-cache/**": true,
    "**/node_modules/**": true,
    "**/tmp/**": true,
    "**/.git": true,
    "**/.svn": true,
    "**/.hg": true,
    "**/CVS": true,
    "**/.DS_Store": true,
    "**/node_modules": true,
    "**/bower_components": true,
    "**/dist/**": true,
    "**/log/**": true,
    "**/logs/**": true,
    "**/.fdk/**": true
  },
  "search.exclude": {
    "**/.git/objects/**": true,
    "**/.git/subtree-cache/**": true,
    "**/node_modules/**": true,
    "**/tmp/**": true,
    "**/.git": true,
    "**/.svn": true,
    "**/.hg": true,
    "**/CVS": true,
    "**/.DS_Store": true,
    "**/node_modules": true,
    "**/bower_components": true,
    "**/dist/**": true,
    "**/log/**": true,
    "package-lock.json": true,
    "yarn.lock": true
  },
  "javascript.updateImportsOnFileMove.enabled": "always",
  "explorer.confirmDelete": false,
  "editor.semanticHighlighting.enabled": false,
  "liveServer.settings.CustomBrowser": "chrome",
  "editor.multiCursorModifier": "ctrlCmd"
}
```

27 OCT 2020
added php to WSL2

```json
{
  "terminal.integrated.shell.windows": "C:\\WINDOWS\\System32\\wsl.exe",
  "terminal.integrated.fontFamily": "Fira Code, Menlo for Powerline",
  "editor.fontFamily": "Fira Code, Consolas, 'Courier New', monospace",
  "workbench.colorTheme": "Community Material Theme Palenight",
  "workbench.editor.highlightModifiedTabs": true,
  "files.autoSave": "afterDelay",
  "editor.fontLigatures": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "php": "html"
  },
  "workbench.iconTheme": "material-icon-theme",
  "editor.wordWrap": "on",
  "window.zoomLevel": 0,
  "editor.tabSize": 2,
  "editor.tabCompletion": "on",
  "diffEditor.ignoreTrimWhitespace": false,
  "explorer.confirmDragAndDrop": false,
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[php]": {
    "editor.defaultFormatter": "junstyle.php-cs-fixer",
    "editor.tabSize": 4
  },
  "php.suggest.basic": false,
  "php-cs-fixer.rules": "@PhpCsFixer",
  "php-cs-fixer.formatHtml": true,
  "editor.minimap.enabled": false,
  "liveServer.settings.donotShowInfoMsg": true,
  "breadcrumbs.enabled": true,
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "editor.formatOnType": true,
  "html.format.wrapLineLength": 80,
  "eslint.alwaysShowStatus": true,
  "files.watcherExclude": {
    "**/.git/objects/**": true,
    "**/.git/subtree-cache/**": true,
    "**/node_modules/**": true,
    "**/tmp/**": true,
    "**/.git": true,
    "**/.svn": true,
    "**/.hg": true,
    "**/CVS": true,
    "**/.DS_Store": true,
    "**/node_modules": true,
    "**/bower_components": true,
    "**/dist/**": true,
    "**/log/**": true,
    "**/logs/**": true,
    "**/.fdk/**": true
  },
  "search.exclude": {
    "**/.git/objects/**": true,
    "**/.git/subtree-cache/**": true,
    "**/node_modules/**": true,
    "**/tmp/**": true,
    "**/.git": true,
    "**/.svn": true,
    "**/.hg": true,
    "**/CVS": true,
    "**/.DS_Store": true,
    "**/node_modules": true,
    "**/bower_components": true,
    "**/dist/**": true,
    "**/log/**": true,
    "package-lock.json": true,
    "yarn.lock": true
  },
  "javascript.updateImportsOnFileMove.enabled": "always",
  "explorer.confirmDelete": false,
  "editor.semanticHighlighting.enabled": false,
  "liveServer.settings.CustomBrowser": "chrome",
  "editor.multiCursorModifier": "ctrlCmd",
  "php-cs-fixer.executablePath": "${extensionPath}/php-cs-fixer.phar",
  "php-cs-fixer.lastDownload": 1603282777942
}
```
