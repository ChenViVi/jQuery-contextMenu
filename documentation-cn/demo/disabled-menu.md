---
currentMenu: disabled-menu 
---

# 示例： Disabled menu


<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript代码示例](#example-code)
- [HTML代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral context-menu-disabled">右键点击我</span>

<button type="button btn btn-neutral" id="toggle-disabled">Enable Menu</button>

## JavaScript代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu({
        selector: '.context-menu-one', 
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
    
    $('#toggle-disabled').on('click', function(e) {
        e.preventDefault();
        var $this = $(this),
            $trigger = $('.context-menu-one');
        if ($trigger.hasClass('context-menu-disabled')) {
            $this.text("Disable Menu");
            $trigger.contextMenu(true);
        } else {
            $this.text("Enable Menu");
            $trigger.contextMenu(false);
        }
    });
});
</script>

## HTML代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>