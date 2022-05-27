# eslint-config-hcwhan-template

在项目中添加配置步骤

1. 安装依赖

一般项目已安装 typescript 在项目中执行命令
``` bash
npm install -D eslint-config-hcwhan eslint prettier husky lint-staged stylelint
// or
yarn add -D eslint-config-hcwhan eslint prettier husky lint-staged stylelint
```

2. 配置 package.json

在项目 package.json 的 scripts 中添加
```
"postinstall": "husky install"
```
同时添加 lint-staged 块
```
  "lint-staged": {
      "*.vue": [
          "eslint --fix --max-warnings 0",
          "prettier --write"
      ],
      "*.{js,ts,json}": [
          "eslint --fix --max-warnings 0",
          "prettier --write"
      ],
      "*.{css,less}": [
          "stylelint --fix --max-warnings 0",
          "prettier --write"
      ]
  }
```

3. 添加 eslint 和 pritter 配置文件

删除项目原有相关配置后
复制 .eslintrc.cjs 和 .prettierrc.cjs 到 项目根目录

4. 添加 husky 配置

在项目中执行 npx husky install 后
复制 .husky/pre-commit 到项目对应目录

5. 添加 vscode 配置

复制 .vscode 到项目根目录
