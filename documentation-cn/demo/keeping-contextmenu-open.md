---
currentMenu: keeping-contextmenu-open 
---

# 示例： 子菜单被点击后不自动隐藏

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
        callback: function(key, options) {
            var m = "你点击了： " + key;
            window.console && console.log(m) || alert(m); 
        },
        items: {
            "edit": {
                name: "点击后菜单隐藏", 
                icon: "edit", 
                callback: function(){ return true; }
            },
            "cut": {
                name: "点击后菜单不隐藏", 
                icon: "cut", 
                callback: function(){ return false; }
            }
        }
    });
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>