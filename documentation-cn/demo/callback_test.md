<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [示例： 菜单点击事件回调方法](#demo-callback)
  - [JavaScript 代码示例](#example-code)
  - [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 示例： 菜单点击事件回调方法

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu({
        selector: '.context-menu-one',
        callback: function(key, options) {
            var message = "来自全局回调方法，你点击了： " + key;
            $('#msg').text(message);
        },
        items: {
            "edit": {
                name: "编辑",
                icon: "edit",
                // 取代全局回调方法
                callback: function(key, options) {
                    var m = "你点击了： 编辑";
                    $('#msg').text(m);
                }
            },
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
<div id="msg"></div>
