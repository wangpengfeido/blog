# 插件

## 通用

### code runner

代码运行插件。

### Color Pick

提示和选取颜色

### copy text

提供一个复制选项，复制时不复制样式`ctrl+shift+c`

### remote-ssh

ssh 工具

## 主题

### One Dark Pro

Atom 暗黑主题。

### vscode icons

改变文件及文件夹图标。

## 快捷键

### Eclipse Keymap

将快捷键设置为 Eclipse 风格。

## git

### Git Graph

git 可视化查看

## TODO

### Todo Tree

列出项目中的 TODO 和 FIXME

### Todo Highlight

TODO 和 FIXME 在代码中高亮显示

## HTML

### auto rename tag

改一边的标签自动改另一边

### open in browser

在浏览器中打开

### live server

开启一个静态资源服务器

## CSS

### color info

提示 css 中的颜色。不建议与 Color Info 一起使用。

### stylelint

css 检查工具

## javascript

### ESLint

EsLint

### prettier-code formatter

替换自带的代码格式化器。可格式化 html、css、js。

可以在项目的`.prettierrc`文件中配置项目 prettier

### EditorConfig for VS Code

代码格式化。通过.editorconfig 配置。

## SASS

### Sass

sass 代码高亮

## react

### vscode-styled-components

styled-components 插件。

## VUE

### vetur

VUE 代码高亮、智能感知、Emmet。

# 我的习惯配置

```json
{
  // 双击打开文件
  "workbench.list.openMode": "doubleClick",
  // tab 空格数 2
  "editor.tabSize": 2,
  // windows上的默认终端
  "terminal.integrated.automationShell.windows": "D:\\software\\Git\\bin\\bash.exe",
  "terminal.integrated.shell.windows": "D:\\software\\Git\\bin\\bash.exe"
}
```

## 可能用到的配置

```json
{
  // 不检查js文件错误
  "javascript.validate.enable": false
}
```

## 快捷键设置

设置快捷键方法：```file => preferences => keyboard shortcuts```

```json
[
  // 禁用：切换到搜索栏
  {
    "key": "ctrl+shift+f",
    "command": "-workbench.view.search",
    "when": "!searchViewletVisible"
  },
  // 禁用：注释。目的：配合 copy text 插件
  {
    "key": "ctrl+shift+c",
    "command": "-editor.action.commentLine",
    "when": "editorTextFocus"
  }
]
```

## 用户代码片段

用户代码片段可使用```命令+tab```快速创建代码。设置方法：```file => preferences => user snippets```

### vue.json

```json
{
  "Print to console": {
    "prefix": "vue",
    "body": [
      "<template>",
      "  <div></div>",
      "</template>",
      "",
      "<script>",
      "export default {",
      "  name: \"\",",
      "};",
      "</script>",
      "",
      "<style>",
      "</style>",
      ""
    ],
    "description": "Log output to console"
  }
}
```

## 待整理

```
    "jpoissonnier.vscode-styled-components",
    "kumar-harsh.graphql-for-vscode",
    "dtsvet.vscode-wasm",
    "cpylua.language-postcss",
    "EditorConfig.editorconfig",
    "dbaeumer.vscode-eslint",
    "drKnoxy.eslint-disable-snippets",
    "mkaufman.htmlhint",
    "streetsidesoftware.code-spell-checker",
    "msjsdiag.debugger-for-chrome",
    "ms-vscode.node-debug2",
    "codezombiech.gitignore",
    "aaron-bond.better-comments",
    "ziyasal.vscode-open-in-github",
    "jasonnutter.search-node-modules",
    "jock.svg",
    "andrejunges.handlebars",
    "bungcip.better-toml",
    "mikestead.dotenv",
    "gruntfuggly.todo-tree",
    "vscode-icons-team.vscode-icons"
```
