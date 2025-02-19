# Formator-Prettier

## 简介

此插件用于格式化less、sass、vue、stylus、ts、yaml代码

此插件需要到[插件市场](https://ext.dcloud.net.cn/plugin?id=2025)下载

## 配置文件

点击菜单【工具】 -> 【设置】 -> 【插件配置】 -> prettier -> prettier.config.js，即可打开配置文件。


## 如何配置格式化选项？

格式化选项配置文件是prettier.config.js,里面对应的选项说明如下：

- printWidth： 控制单行最大长度
- semi： 控制每条语句是否加上分号
- tabWidth： 控制一个tab对应的空格数
- useTabs： 控制缩进用tab还是space
- singleQuote：控制字符串是用单引号还是双引号
- trailingComma： 是否去掉末尾的逗号
- bracketSpacing： 控制json对象括号前后是否加上空格

详细的配置说明可以参考[options](https://prettier.io/docs/en/options.html)

## 如何支持新的语言？
1. 修改package.json配置，添加要支持的新的语言的文件后缀
~~~
"contributes": {
    "formator": {
        "name": "Prettier",
        "class": "prettier_service.js",
        "filetypes": [
            "less",
            "sass",
            "scss",
            "vue",
            "ux",
            "ts",
            "foo"//文件后缀名
        ]
    }
}
~~~
2. 修改prettier.config.js,将新添加的语言配置到对应的格式化处理器上。
~~~
parsers: {
    ".jsx": "flow",
    ".scss": "scss",
    ".ts": "typescript",
    ".less": "css",
    ".vue": "vue",
    ".ux": "vue",
    ".yml": "yaml",
    ".foo":"flow"//文件后缀名对应的格式化处理器
}
~~~

## 示例Gif

<img src="/static/snapshots/tutorial/prettier.gif" style="zoom:80%; border: 1px solid #eee;" />