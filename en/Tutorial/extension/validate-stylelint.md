# validate-stylelint

## Introduction

validate-stylelint, used to verify the syntax of `css`, `less`, `scss`.

This plugin needs to be installed at [HBuilderX Plugin Market](https://ext.dcloud.net.cn/plugin?name=validate-stylelint).

## Configuration file

Menu [Settings] -> [Plugin Configuration] -> [stylelint], click on `.stylelintrc.js` to open the configuration file.
  
<img src="/static/snapshots/plugins/plugin_setting_en.png" style="zoom: 45%; border: 1px solid #eee;border-radius: 20px;"/>

## Rule configuration

There are hundreds of rules in stylelint, which can be divided into three categories:

- `Rules for proofreading style` (mainly for spaces (such as spaces near colons), line breaks, indentation, etc.)
- `Rules for judging the maintainability of the cod`e (judging whether a certain ID is used in the CSS selector, or whether the !important keyword is applied in a statement)
- `Rules for judging code errors` (check whether the wrong HEX color writing or whether a certain abbreviated attribute will cover other declaration statements)

The rule attribute is an object, the key is the name of the rule, and the value is the rule configuration. Each rule configuration conforms to one of the following formats:

- `Single value` (primary option)
- `An array with two values` ([primary option,secondary option])
- `null` (close rule)

## Add rules

Modify the `.stylelintrc.js` file and add options:

```javascript

  module.exports = {
    "extends": "stylelint-config-recommended",
    "rules":{
        "unit-no-unknown": false,
        "indentation": "tab",       
        "unit-no-unknown": true,
        "color-hex-case": [
          "lower", {
          "message": "Lowercase letters are easier to distinguish from numbers"
          }
        ],
        "max-empty-lines": 2,
        "unit-whitelist": ["em", "rem", "%", "s", "px", "upx"],
        "number-leading-zero": null
    }
  }

```

## More configuration rules

Detailed configuration instructions: [https://stylelint.io](https://stylelint.io/user-guide/rules/)