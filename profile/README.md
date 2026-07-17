# hi-tpext👋

国内备份：<https://www.gitlink.org.cn/hi-tpext>

codeberg：<https://codeberg.org/hi-tpext>

## 近期动态

|  扩展           | 更新   | 日期 |
|  ----           | ----  |----  |
|tp8.1/webman2.1| 支持多语言i18n|2026-06|
|tp8.1/webman2.1| pgsql支持|2026-05|
| tpext-myadmin[5.2.x/4.5.x]   |采用vue3构建页面|2025-09|
| tpext-vexipui   |vue3 UI库，可替换tpextbuilder|2025-02|
| tpextbuilder    |Image组件显示缩略图|2025-01|
| tpext-cms       |进一步完善，除静态生成外，新增支持动态解析|2024-12|
| tpextbuilder    |增加`tableHelper`，用于显示表格页面|2024-11|
| tpext-tinyvue   |vue3 UI库，可替换tpextbuilder|2024-07|

## 各版本依赖汇总
|  平台           | 依赖   | 备注 |
|  ----           | ----  |----  |
||php7.1+|:x:不推荐|
| tp5.1+   |"ichynul/tpextmyadmin": "^1.9"|UI默认使用ichynul/tpextbuilder :x: 不可替换|
| tp6.1+   |"ichynul/tpextmyadmin": "^3.5"|UI默认使用ichynul/tpextbuilder :white_check_mark: 可替换|
| webman1.5   |"ichynul/tpextmyadmin": "^4.3"|UI默认使用ichynul/tpextbuilder :white_check_mark: 可替换|
||php8.1+|:white_check_mark:推荐|
| tp8.1+   |"ichynul/tpextmyadmin": "^5.2"|UI默认ichynul/tpextbuilder :white_check_mark: 可替换，支持pqsql、支持多语言i18n|
| webman2.1+   |"ichynul/tpextmyadmin": "^4.5"|UI默认ichynul/tpextbuilder :white_check_mark: 可替换，支持pqsql、支持多语言i18n|

### `ichynul/tpextmyadmin v5`早期版本(5.0、5.1)支持tp6安装，但建议退回到v3

## 如何替换默认的UI依赖`ichynul/tpextbuilder`？

注意，上面表格中标明`可替换`时才可以，并且确保`ichynul/tpextmyadmin`是最新的，老版本可能不支持

编辑网站根目录的`composer.json`文件
```json
"require":{
    "topthink/framework": "^8.1",
    "ichynul/tpextmyadmin": "^5.2",
    "tpext-tinyvue": "^5.1",//添加
    "tpext-vexipui": "^5.1",//或者这个，二者选其一
}
```
然后 运行 `composer u`

## 如何切换语言？(How to switch languages?)

### thinkphp

`config/lang.php`:

```php
return [
    'default_lang' => 'zh-cn',// en
    //...
];
```

### webman

`config/plugin/tpext/core/lang.php`:

```php
return [
    'default_lang' => 'zh-cn',// en
    //...
];
```
