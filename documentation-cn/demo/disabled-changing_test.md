<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [示例： 改变菜单项](#demo-disabled-changing)
  - [JavaScript 代码示例](#example-code)
  - [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 示例： 改变菜单项

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu({
        selector: '.context-menu-one', 
        callback: function(key, options) {
            var message = ""你点击了： " + key;
            $('#msg').text(message); 
        },
        items: {
            "edit": {name: "可点击", icon: "edit"},
            "cut": {
                name: "已禁用", 
                icon: "cut", 
                disabled: function(key, opt) { 
                    // this references the trigger element
                    return !this.data('cutDisabled'); 
                }
            },
            "toggle": {
                name: "切换", 
                callback: function() {
                    // this references the trigger element
                    this.data('cutDisabled', !this.data('cutDisabled'));
                    return false;
                }
            }
        }
    });
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
<div id="msg"></div>