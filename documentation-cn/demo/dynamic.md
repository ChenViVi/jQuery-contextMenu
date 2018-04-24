---
currentMenu: dynamic 
---

# 示例： 为菜单增加新的触发器

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

`jQuery.contextMenu` 让你能在触发器元素可用之前定义 &lt;menu&gt;


<div> 
  <button id="add-trigger" class="btn btn-default" type="submit">Button</button>    
</div>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    // add new trigger
    $('#add-trigger').on('click', function(e) {
        $('<div class="context-menu-one clear btn btn-neutral menu-injected">'
            + '右键点击我 <em>（动态添加的）</em>'
            + '</div><br>').insertBefore(this);
        // 不需要再次初始化 $.contextMenu 了 :)
    });
    
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
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>