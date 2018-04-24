---
currentMenu: dynamic-create 
---

# 示例： 动态加载菜单

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu({
        selector: '.context-menu-one', 
        build: function($trigger, e) {
            // 每次菜单出现，此方法都会执行
            // 每次菜单隐藏，返回值都会被销毁
            // is the original contextmenu event, containing e.pageX and e.pageY (amongst other data)
            return {
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
            };
        }
    });
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
