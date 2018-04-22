---
currentMenu: trigger-custom  
---

# 示例： Custom Activated Context Menu

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript代码示例](#example-code)
- [HTML代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral">press that button</span>

<button id="activate-menu" class="btn btn-default" type="submit">Button</button>

## JavaScript代码示例

<script type="text/javascript" class="showcase">
$(function(){
    // make button open the menu
    $('#activate-menu').on('click', function(e) {
        e.preventDefault();
        $('.context-menu-one').contextMenu();
        // or $('.context-menu-one').trigger("contextmenu");
        // or $('.context-menu-one').contextMenu({x: 100, y: 100});
    });
    
    $.contextMenu({
        selector: '.context-menu-one', 
        trigger: 'none',
        callback: function(key, options) {
            var m = "clicked: " + key;
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
});
</script>

## HTML代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>