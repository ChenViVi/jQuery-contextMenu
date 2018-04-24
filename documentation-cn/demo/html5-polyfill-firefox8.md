---
currentMenu: html5-polyfill-firefox8 
---

# 示例： HTML5 Polyfill (Firefox)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral" contextmenu="html5firefox8">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu('html5');
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>

```html
<menu id="html5firefox8" type="context" >
  <menuitem label="旋转" onclick="alert('旋转')" hint="我是一条提示"></menuitem>
  <menuitem label="调整大小" onclick="alert('调整大小')"></menuitem>
  <menuitem label="已禁用" onclick="alert('已禁用')" disabled></menuitem>
  <menu label="分享">
    <menuitem label="twitter" onclick="alert('twitter')"></menuitem>
    <menuitem label="facebook" onclick="alert('facebook')"></menuitem>
    <hr>
    <menuitem type="checkbox" label="(checkbox) 是或否" 
        onclick="alert('checkbox: ' + (this.checked ? '是' : '否'))"></menuitem>
    <hr>
    <menuitem type="radio" label="(radio) 是" radiogroup="alpha" checked 
        onclick="alert('radio: 是')"></menuitem>
    <menuitem type="radio" label="(radio) 否" radiogroup="alpha" 
        onclick="alert('radio: 否')"></menuitem>
  </menu>
</menu>
```


<menu id="html5firefox8" type="context">
  <menuitem label="旋转" onclick="alert('旋转')" hint="我是一条提示"></menuitem>
  <menuitem label="调整大小" onclick="alert('调整大小')"></menuitem>
  <menuitem label="已禁用" onclick="alert('已禁用')" disabled></menuitem>
  <menu label="分享">
    <menuitem label="twitter" onclick="alert('twitter')"></menuitem>
    <menuitem label="facebook" onclick="alert('facebook')"></menuitem>
    <hr>
    <menuitem type="checkbox" label="(checkbox) 是或否" 
        onclick="alert('checkbox: ' + (this.checked ? '是 : '否'))"></menuitem>
    <hr>
    <menuitem type="radio" label="(radio) 是 " radiogroup="alpha" checked 
        onclick="alert('radio: 是 ')"></menuitem>
    <menuitem type="radio" label="(radio) 否" radiogroup="alpha" 
        onclick="alert('radio: 否')"></menuitem>
  </menu>
</menu>