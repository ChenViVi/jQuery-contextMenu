---
currentMenu: html5-polyfill
---

# 示例： HTML5 Polyfill

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

`jQuery.contextMenu` 让你能导入 HTML5 的  &lt;menu&gt; 结构，使得其能在低版本浏览器中使用

<span class="context-menu-one btn btn-neutral" contextmenu="html5polyfill">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu('html5');
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>

```html
<menu id="html5polyfill" type="context" style="display:none">  
    <command label="旋转" onclick="alert('旋转')" icon="images/cut.png">
    <command label="调整大小" onclick="alert('调整大小')" icon="images/door.png">
    <menu label="分享">
        <command label="twitter" onclick="alert('twitter')" icon="images/page_white_copy.png">
        <hr>
        <command label="facebook" onclick="alert('facebook')" icon="images/page_white_edit.png">
        <hr>
        <label>foo bar<input type="text" name="foo"></label>
    </menu>
</menu>
```

<menu id="html5polyfill" type="context" style="display:none">  
    <command label="旋转" onclick="alert('旋转')" icon="images/cut.png">
    <command label="调整大小" onclick="alert('调整大小')" icon="images/door.png">
    <menu label="分享">
        <command label="twitter" onclick="alert('twitter')" icon="images/page_white_copy.png">
        <hr>
        <command label="facebook" onclick="alert('facebook')" icon="images/page_white_edit.png">
        <hr>
        <label>foo bar<input type="text" name="foo"></label>
    </menu>
</menu>
