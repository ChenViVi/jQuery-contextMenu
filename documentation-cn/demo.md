---
currentMenu: simple-context-menu
---

# 示例：快捷菜单的简单使用

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例: 快捷菜单的简单使用](#example-code-simple-context-menu)
- [HTML 代码示例: 快捷菜单的简单使用](#example-html-simple-context-menu)
- [jQuery Context Menu 示例集合](#jquery-context-menu-demo-gallery)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例：快捷菜单的简单使用

<script type="text/javascript" class="showcase">
    $(function() {
        $.contextMenu({
            selector: '.context-menu-one',
            callback: function(key, options) {
                var m = "clicked: " + key;
                window.console && console.log(m) || alert(m);
            },
            items: {
                "edit": {name: "编辑", icon: "edit"},
                "cut": {name: "剪切", icon: "cut"},
               copy: {name: "复制", icon: "copy"},
                "paste": {name: "粘贴", icon: "paste"},
                "delete": {name: "删除", icon: "delete"},
                "sep1": "---------",
                "quit": {name: "退出", icon: function(){
                    return 'context-menu-icon context-menu-icon-quit';
                }}
            }
        });

        $('.context-menu-one').on('click', function(e){
            console.log('你点击了：', this);
        })    
    });
</script>

## HTML 代码示例：菜单的简单使用
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>

## jQuery Context Menu 示例集合

*   [菜单的简单使用](demo.html)
*   [DOM元素调用菜单](demo/on-dom-element.html)
*   [为菜单增加新的触发器](demo/dynamic.html)
*   [动态加载菜单](demo/dynamic-create.html)
*   [异步加载菜单](demo/async-create.html)
*   [子菜单被点击后不自动隐藏](demo/keeping-contextmenu-open.html)
*   [菜单点击事件回调方法](demo/callback.html)
*   [通过左键点击触发菜单](demo/trigger-left-click.html)
*   [在触控设备上通过滑动触发菜单](demo/trigger-swipe.html)
*   [通过鼠标悬停动作触发菜单](demo/trigger-hover.html)
*   [通过鼠标悬停动作触发菜单并自动隐藏](demo/trigger-hover-autohide.html)
*   [自定义菜单的触发器](demo/trigger-custom.html)
*   [禁用菜单](demo/disabled-menu.html)
*   [禁用菜单项](demo/disabled.html)
*   [禁用回调方法](demo/disabled-callback.html)
*   [改变菜单项](demo/disabled-changing.html)
*   [Accesskeys（键盘快捷键）](demo/accesskeys.html)
*   [多级菜单](demo/sub-menus.html)
*   [带表单的菜单](demo/input.html)
*   [自定义菜单项](demo/custom-command.html)
*   [带标题的菜单](demo/menu-title.html)
*   [导入 HTML5 中的menu元素<menu type="context">](demo/html5-import.html)
*   [HTML5 Polyfill](demo/html5-polyfill.html)
*   [HTML5 Polyfill (Firefox)](demo/html5-polyfill-firefox8.html)
