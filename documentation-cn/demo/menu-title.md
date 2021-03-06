---
currentMenu: menu-title  
---

# 示例： 带标题的菜单


<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [CSS 代码示例](#example-css)
- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


<span class="context-menu-one btn btn-neutral">右键点击我</span>
<span class="context-menu-two btn btn-neutral">右键点击我</span>
<span class="context-menu-three btn btn-neutral">右键点击我</span>



## CSS 代码示例

<style type="text/css" class="showcase">
    /* 菜单标题 */

​    .css-title:before {
        content: "由 CSS 生成的标题";
        display: block;
        position: absolute;
        top: 0;
        right: 0;
        left: 0;
        background: #DDD;
        padding: 2px;


        font-family: Verdana, Arial, Helvetica, sans-serif;
        font-size: 11px;
        font-weight: bold;
    }
    .css-title :first-child {
        margin-top: 20px;
    }

    /* 由 data attribute 生成标题 */
    .data-title:before {
        content: attr(data-menutitle);
        display: block;
        position: absolute;
        top: 0;
        right: 0;
        left: 0;
        background: #DDD;
        padding: 2px;

        font-family: Verdana, Arial, Helvetica, sans-serif;
        font-size: 11px;
        font-weight: bold;
    }
    .data-title :first-child {
        margin-top: 20px;
    }
</style>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    // register regular menu
    $.contextMenu({
        selector: '.context-menu-one',
        callback: function(key, options) {
            var m = "你点击了： " + key;
            window.console && console.log(m) || alert(m);
        },
        items: {
            "edit": {name: "编辑", icon: "edit"},
            "cut": {name: "剪切", icon: "cut"},
            "copy": {name: "复制", icon: "copy"},
            "paste": {name: "粘贴", icon: "paste"},
            "delete": {name: "删除", icon: "delete"},
            "sep1": "---------",
            "quit": {name: "退出", icon: function($element, key, item){ return 'context-menu-icon context-menu-icon-quit'; }}
        }
    });

    // 由 CSS 生成菜单标题
    $.contextMenu({
        selector: '.context-menu-two',
        className: '由 CSS 生成的标题',
        callback: function(key, options) {
            var m = "你点击了： " + key;
            window.console && console.log(m) || alert(m);
        },
        items: {
            "edit": {name: "编辑", icon: "edit"},
            "cut": {name: "剪切", icon: "cut"},
            "copy": {name: "复制", icon: "copy"},
            "paste": {name: "粘贴", icon: "paste"},
            "delete": {name: "删除", icon: "delete"},
            "sep1": "---------",
            "quit": {name: "退出", icon: function($element, key, item){ return 'context-menu-icon context-menu-icon-quit'; }}
        }
    });

    // 由 data-attribute 生成菜单标题
    $.contextMenu({
        selector: '.context-menu-three',
        className: 'data-title',
        callback: function(key, options) {
            var m = "你点击了： " + key;
            window.console && console.log(m) || alert(m);
        },
        items: {
            "edit": {name: "编辑", icon: "edit"},
            "cut": {name: "剪切", icon: "cut"},
            "copy": {name: "复制", icon: "copy"},
            "paste": {name: "粘贴", icon: "paste"},
            "delete": {name: "删除", icon: "delete"},
            "sep1": "---------",
            "quit": {name: "退出", icon: function($element, key, item){ return 'context-menu-icon context-menu-icon-quit'; }}
        }
    });

    // 由 JS 生成标题
    $('.data-title').attr('data-menutitle', "由 JS 生成的标题");
});
</script>

## HTML 代码示例

```html
<span class="context-menu-one btn btn-neutral">右键点击我</span>

<span class="context-menu-two btn btn-neutral">右键点击我</span>

<span class="context-menu-three btn btn-neutral">右键点击我</span>
```
