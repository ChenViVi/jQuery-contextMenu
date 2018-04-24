---
currentMenu: custom-command 
---

# 示例： 自定义菜单项

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    /**************************************************
     * 自定义自定义菜单项
     **************************************************/
    $.contextMenu.types.label = function(item, opt, root) {
        // this === item.$node

        $('<span>Label<ul>'
            + '<li class="label1" title="label 1">label 1</li>'
            + '<li class="label2" title="label 2">label 2</li>'
            + '<li class="label3" title="label 3">label 3</li>'
            + '<li class="label4" title="label 4">label 4</li></ul></span>')
            .appendTo(this)
            .on('click', 'li', function() {
                // 在这里自定义点击事件操作
                console.log('你点击了：' + $(this).text());
                // 隐菜单
                root.$menu.trigger('contextmenu:hide');
            });
            
        this.addClass('labels').on('contextmenu:focus', function(e) {
            // 菜单获得焦点事件，在这里做自定义菜单项的操作
        }).on('contextmenu:blur', function(e) {
            // 菜单失去焦点事件，在这里做自定义菜单项的销毁操作
        }).on('keydown', function(e) {
            // 菜单键盘按下事件
        });
    };
    
    /**************************************************
     * 使用"label"来将以上内容加入菜单
     **************************************************/
    $.contextMenu({
        selector: '.context-menu-one', 
        callback: function(itemKey, opt, rootMenu, originalEvent) {
            var m = "你点击了： " + key;
            window.console && console.log(m) || alert(m); 
        },
        items: {
            open: {name: "打开", callback: $.noop},
            label: {type: "标签", customName: "Label"},
            edit: {name: "编辑", callback: $.noop}
        }
    });
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>

<style type="text/css" class="showcase">
    .labels > span > ul {
        margin: 0; 
        padding: 0;
        list-style: none;
        display: block;
        float: none;
    }
    .labels > span > ul > li {
        display: inline-block;
        width: 20px;
        height: 20px;
        border: 1px solid #CCC;
        overflow: hidden;
        text-indent: -2000px;
    }
    .labels > span > ul > li.selected,
    .labels > span > ul > li:hover { border: 1px solid #000; }
    .labels > span > ul > li + li { margin-left: 5px; }
    .labels > span > ul > li.label1 { background: red; }
    .labels > span > ul > li.label2 { background: green; }
    .labels > span > ul > li.label3 { background: blue; }
    .labels > span > ul > li.label4 { background: yellow; }
</style>
