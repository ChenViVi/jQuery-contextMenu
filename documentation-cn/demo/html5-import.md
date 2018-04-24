---
currentMenu: html5-import
---

# 示例： 导入 HTML5 中的 menu 元素 `<menu type="context">`

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

`jQuery.contextMenu` 让你能导入 HTML5 的  `<menu>` 结构，使得其能在低版本浏览器中使用 

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu({
        selector: '.context-menu-one',
        items: $.contextMenu.fromMenu($('#html5menu'))
    });
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>

```html
<menu id="html5menu" style="display:none" class="showcase">
  <command label="旋转" icon="edit" onclick="alert('旋转')">
  <command label="调整大小" onclick="alert('调整大小')">
    <command label="twitter" onclick="alert('twitter')">
    <hr>
    <command label="facebook" onclick="alert('facebook')">
  </menu>
</menu>
```

<menu id="html5menu" type="context" style="display:none">
  <command label="旋转" icon="edit" onclick="alert('旋转')">
  <command label="调整大小" onclick="alert('调整大小')">
    <command label="twitter" onclick="alert('twitter')">
    <hr>
    <command label="facebook" onclick="alert('facebook')">
  </menu>
</menu>
