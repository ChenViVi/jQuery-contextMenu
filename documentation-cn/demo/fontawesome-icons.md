---
currentMenu: accesskeys
---

# 示例： FontAwesome icons

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript代码示例](#example-code)
- [HTML代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

The menu allows you to use [FontAwesome](http://fontawesome.io/) [icons](http://fontawesome.io/icons/) in your menu. Just include the CSS for FontAwesome and you are ready to go.

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript代码示例

<script type="text/javascript" class="showcase">
 $(function() {
    $.contextMenu({
        selector: '.context-menu-one',
        callback: function(key, options) {
            var m = "clicked: " + key;
            window.console && console.log(m) || alert(m);
        },
        items: {
            "edit": {name: "编辑", icon: "fa-edit"},
            "cut": {name: "Beer", icon: "fa-beer"},
            copy: {name: "Cloud download", icon: "fa-cloud-download"},
            "paste": {name: "Certificate", icon: "fa-certificate"}
        }
    });

    $('.context-menu-one').on('click', function(e){
        console.log('clicked', this);
    })
});
</script>

## HTML代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
