<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [示例： Disabled Callback](#demo-disabled-callback)
  - [JavaScript代码示例](#example-code)
  - [HTML代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 示例： Disabled Callback

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu({
        selector: '.context-menu-one', 
        callback: function(key, options) {
            var message = "clicked: " + key;
            $('#msg').text(message); 
        },
        items: {
            "edit": {
                name: "Clickable", 
                icon: "edit", 
                disabled: function(){ return false; }
            },
            "cut": {
                name: "Disabled", 
                icon: "cut", 
                disabled: function(){ return true; }
            }
        }
    });
});
</script>

## HTML代码示例

<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
<div id="msg"></div>