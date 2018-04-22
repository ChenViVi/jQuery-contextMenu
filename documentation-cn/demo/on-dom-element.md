---
currentMenu: on-dom-element
---

# 示例： Context Menu on DOM Element

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript代码示例](#example-code)
- [HTML代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<ul id="the-node">
    <li><span class="context-menu-one btn btn-neutral">右键点击我 1</span></li>
    <li><span class="context-menu-one btn btn-neutral">右键点击我 2</span></li>
    <li>右键点击我 3</li>
    <li>右键点击我 4</li>
</ul>

## JavaScript代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $('#the-node').contextMenu({
        selector: 'li', 
        callback: function(key, options) {
            var m = "clicked: " + key + " on " + $(this).text();
            window.console && console.log(m) || alert(m); 
        },
        items: {
            "edit": {name: "Edit", icon: "edit"},
            "cut": {name: "Cut", icon: "cut"},
            "copy": {name: "Copy", icon: "copy"},
            "paste": {name: "Paste", icon: "paste"},
            "delete": {name: "Delete", icon: "delete"},
            "sep1": "---------",
            "quit": {name: "Quit", icon: function($element, key, item){ return 'context-menu-icon context-menu-icon-quit'; }}
        }
    });
});
</script>

## HTML代码示例

```html
<ul id="the-node">
    <li><span class="context-menu-one btn btn-neutral">右键点击我 1</span></li>
    <li><span class="context-menu-one btn btn-neutral">右键点击我 2</span></li>
    <li>右键点击我 3</li>
    <li>右键点击我 4</li>
</ul>

```
