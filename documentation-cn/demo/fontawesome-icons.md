---
currentMenu: accesskeys
---

# 示例： FontAwesome 图标

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

只要你导入了 FontAwesome 的  CSS，你就可以在菜单中使用 [FontAwesome](http://fontawesome.io/) [图标](http://fontawesome.io/icons/) ，

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
 $(function() {
    $.contextMenu({
        selector: '.context-menu-one',
        callback: function(key, options) {
            var m = "你点击了： " + key;
            window.console && console.log(m) || alert(m);
        },
        items: {
            "edit": {name: "编辑", icon: "fa-edit"},
            "cut": {name: "啤酒", icon: "fa-beer"},
            copy: {name: "云下载", icon: "fa-cloud-download"},
            "paste": {name: "证书", icon: "fa-certificate"}
        }
    });

    $('.context-menu-one').on('click', function(e){
        console.log('你点击了：', this);
    })
});
</script>

## HTML代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
