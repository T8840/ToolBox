# ToolBox

## Introduction
Use Vue-cli4 and chrome-ext to build Chrome Extention
- **搭建环境**
    - 创建一个vue-cli4项目： vue create vue-extension，对话流程选择默认就行。
    - 进入项目cd vue-extension
    - 安装vue-cli-plugin-chrome-ext插件：vue add chrome-ext,根据安装对话选项设置好。
    - 删除vue-cli3无用文件跟文件夹：src/main.js，public、src/components
- **运行项目**
    - `npm run build-watch` 运行开发环境，对修改文件进行实时编译并自动在根目录下生成 `dist` 文件夹，然后在浏览器上加载 `dist` 文件夹完成插件安装。(注意：修改 `background` 文件跟 `manifest.json` 文件并不能实时刷新代码，需要重新加载插件才行—这里通过在浏览器扩展程序点击刷新按钮就可以重新加载插件代码)
    - npm run build 运行生产环境编译打包，将所有文件进行整合打包


## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your unit tests
```
npm run test:unit
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
