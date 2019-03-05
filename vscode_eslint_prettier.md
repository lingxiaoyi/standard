# VsCode 开发环境配置规范

为了保证团队代码风格统一，请务必按照此配置规范进行配置。

## 目录

- [一、下载安装 vscode 和插件](#一、下载安装-vscode-和插件)
- [二、配置 vscode](#二、配置-vscode)
- [三、配置 editorconfig](#三、配置-editorconfig)
- [四、项目配置](#四、项目配置)
  - [自定义项目配置](#自定义项目配置)
  - [vue 项目配置](#vue-项目配置)
  - [react 项目配置](#react-项目配置)
- [五、代码提交前自动格式化配置](#五、代码提交前自动格式化配置)
- [六、问题反馈](#六、问题反馈)
- [七、主题插件推荐](#七、主题插件推荐)

## 一、下载安装 vscode 和插件

[点击下载 vscode](https://code.visualstudio.com/)

安装插件

- [eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)：js 代码检查工具
- [prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)：代码格式化工具
- [editorconfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)：帮助开发人员在不同的编辑器和 IDE 之间定义和维护一致的编码样式
- [stylelint](https://marketplace.visualstudio.com/items?itemName=shinnn.stylelint)：css 代码检查工具

## 二、配置 vscode

`code -> 首选项 -> 设置 -> 用户设置` 添加以下配置项

```json
{
  // 使用2个空格代替一个tab操作（必选）
  "editor.tabSize": 2,
  // js中使用单引号（必选）
  "prettier.singleQuote": true,
  // 配置打印宽度为120，超过120代码自动换行。（必选）
  "prettier.printWidth": 120,
  // 保存时自动修复（必选）
  "eslint.autoFixOnSave": true,
  // 添加对vue文件的检查（开发vue项目必选）
  "eslint.validate": ["javascript", "javascriptreact", { "autoFix": true, "language": "vue" }],

  // 保存自动格式化（可选，如果不喜欢工具自动格式化，可以用手动使用快捷键格式化之后再手动保存）
  "editor.formatOnSave": true,
  // 排除js文件的自动格式化（避免与eslint自动修复冲突）（与上一配置配合使用）
  "[javascript]": {
    "editor.formatOnSave": false
  },
  // markdownlint配置（可选）
  "markdownlint.config": {
    "MD029": false // fix this: https://github.com/DavidAnson/markdownlint/issues/45
  }
}
```

## 三、配置 editorconfig

项目根目录添加`.editorconfig`文件，内容如下：

```bash
# https://editorconfig.org
root = true

# 格式规范，请直接复制使用，勿修改。
[*]
charset = utf-8
end_of_line = lf
indent_size = 2
indent_style = space
insert_final_newline = true
max_line_length = 120
tab_width = 2
trim_trailing_whitespace = true
```

## 四、项目配置

### 自定义项目配置

> 完整示例项目地址：[http://codeio.dftoutiao.com/RESEARCH/standard-demo](http://codeio.dftoutiao.com/RESEARCH/standard-demo)

- 安装 npm 包

`eslint`、`babel-eslint`、`prettier`、`eslint-config-prettier`、`eslint-plugin-prettier`

```bash
# 生成package.json
npm init -y

# 安装依赖
npm i -D eslint babel-eslint eslint-config-prettier eslint-plugin-prettier
npm i -D -E prettier
```

- 配置 prettier（.prettierrc.js）

```javascript
module.exports = {
  singleQuote: true,
  printWidth: 120,
  tabWidth: 2,
  semi: true
};
```

- 配置 eslint（.eslintrc.js）

```javascript
module.exports = {
  root: true,
  // 环境配置（根据实际情况做取舍）
  env: {
    browser: true,
    node: true,
    commonjs: true,
    es6: true,
    jquery: true
  },
  // 添加项目使用到的全局变量，按需添加。
  globals: {
    SLAPP: true,
    SL: true
  },
  // 继承eslint的默认配置和prettier的配置。
  extends: ['eslint:recommended', 'plugin:prettier/recommended'],
  // 支持babel的使用
  parser: 'babel-eslint',
  parserOptions: {
    // 支持es6模块语法
    sourceType: 'module'
  },
  // 自定义规则（优先级最高）
  rules: {
    'prettier/prettier': [
      'error',
      {
        singleQuote: true,
        printWidth: 120,
        tabWidth: 2,
        semi: true
      }
    ],
    'no-console': 'off'
  }
};
```

- 配置 eslint 检查忽略文件（.eslintignore）

```bash
# eslint默认不会检查node_modules里面的代码，所以这里添加不检查打包后dist下的代码和src下已经压缩的库文件代码
/dist
/src/**/*.min.js
```

- 配置 gitignore

项目根目录添加`.gitignore`文件，内容如下：

```bash
# Created by https://www.gitignore.io/api/code,node,macos

### Code ###
# Visual Studio Code - https://code.visualstudio.com/
.settings/
.vscode/
tsconfig.json
jsconfig.json

### macOS ###
# General
.DS_Store
.AppleDouble
.LSOverride

# Thumbnails
._*

### Node ###
# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Runtime data
pids
*.pid
*.seed
*.pid.lock

# Compiled binary addons (https://nodejs.org/api/addons.html)
build/Release

# Dependency directories
node_modules/
jspm_packages/

# TypeScript v1 declaration files
typings/

# Optional npm cache directory
.npm

# Optional eslint cache
.eslintcache

# Output of 'npm pack'
*.tgz

# Yarn Integrity file
.yarn-integrity

# dotenv environment variables file
.env

# parcel-bundler cache (https://parceljs.org/)
.cache

# next.js build output
.next

# nuxt.js build output
.nuxt
```

### vue 项目配置

基于大部分人都会针对 vue 项目安装[vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)插件，为了避免冲突带来的困惑，请在 vscode 工具中添加如下配置：

```json
"prettier.disableLanguages": [],
"vetur.format.defaultFormatter.html": "none",
"vetur.format.defaultFormatter.css": "none",
"vetur.format.defaultFormatter.postcss": "none",
"vetur.format.defaultFormatter.scss": "none",
"vetur.format.defaultFormatter.less": "none",
"vetur.format.defaultFormatter.stylus": "none",
"vetur.format.defaultFormatter.js": "none",
"vetur.format.defaultFormatter.ts": "none"
```

1. 安装依赖包

```bash
npm i -D eslint babel-eslint eslint-config-prettier eslint-plugin-prettier
npm i -D -E prettier
```

2. 项目根目录添加文件`.prettierrc.js`

```javascript
module.exports = {
  singleQuote: true,
  printWidth: 120,
  tabWidth: 2,
  semi: true
};
```

3. 配置 eslint

- 如果是使用 [Vue CLI 3](https://cli.vuejs.org/) 创建的项目，修改`package.json`中的配置项`eslintConfig`

```json
{
  // ...
  "eslintConfig": {
    "root": true,
    "env": {
      "node": true,
      "browser": true
    },
    "extends": ["eslint:recommended", "plugin:vue/essential", "plugin:prettier/recommended"],
    "rules": {
      "prettier/prettier": [
        "error",
        {
          "singleQuote": true,
          "printWidth": 120,
          "tabWidth": 2,
          "semi": true
        }
      ],
      "no-console": "off"
    },
    "parserOptions": {
      "parser": "babel-eslint"
    }
  }
  // ...
}
```

- 如果使用 [Vue CLI 2](https://github.com/vuejs/vue-cli/tree/v2#vue-cli--) 创建的项目，修改`.eslintrc.js`

```javascript
module.exports = {
  root: true,
  parserOptions: {
    parser: 'babel-eslint'
  },
  env: {
    node: true,
    browser: true
  },
  extends: ['eslint:recommended', 'plugin:vue/essential', 'plugin:prettier/recommended'],
  plugins: ['vue'],
  rules: {
    'prettier/prettier': [
      'error',
      {
        singleQuote: true,
        printWidth: 120,
        tabWidth: 2,
        semi: true
      }
    ],
    'no-console': 'off'
  }
};
```

> 点击查看示例：[Vue CLI 3](http://codeio.dftoutiao.com/RESEARCH/standard-demo/src/vue)、[Vue CLI 2](http://codeio.dftoutiao.com/RESEARCH/standard-demo/src/vue2)

### react 项目配置

如果是使用[create-react-app](https://github.com/facebook/create-react-app)创建的项目，做如下调整：

1. 安装依赖包

```bash
# 使用npm
npm i -D eslint-config-prettier eslint-plugin-prettier
npm i -D -E prettier
# 使用yarn
yarn add -D eslint-config-prettier eslint-plugin-prettier
yarn add -D -E prettier
```

2. 项目根目录添加文件`.prettierrc.js`

```javascript
module.exports = {
  singleQuote: true,
  printWidth: 120,
  tabWidth: 2,
  semi: true
};
```

3. 修改`package.json`中的配置项`eslintConfig`

```json
{
  // ...
  "eslintConfig": {
    "extends": ["eslint:recommended", "react-app", "plugin:prettier/recommended"],
    "rules": {
      "prettier/prettier": [
        "error",
        {
          "singleQuote": true,
          "printWidth": 120,
          "tabWidth": 2,
          "semi": true
        }
      ],
      "no-console": "off"
    }
  }
  // ...
}
```

> 点击查看示例：[react](http://codeio.dftoutiao.com/RESEARCH/standard-demo/src/react)

## 五、代码提交前自动格式化配置

安装依赖包

```bash
npm i -D husky lint-staged
```

修改`package.json`配置

```json
{
  // ...,
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "linters": {
      "src/**/*.{js,jsx,ts,tsx,json,css,scss,md}": [
        "prettier --single-quote --semi --print-width 120 --tab-width 2 --write",
        "git add"
      ]
    },
    "ignore": ["src/**/*.min.js"]
  }
  // ...
}
```

配好后提交代码时会自动将代码格式化

## 六、问题反馈

由于 react 脚手架`create-react-app` 和 vue 脚手架`vue-cli`的不断升级，在配置过程中可能会遇到一些问题，如有问题可以直接找我反馈，也欢迎提工单（issue）或者提合并请求（PR）。

## 七、主题插件推荐

[vscode 主题插件推荐](./vscode_ext.md)
