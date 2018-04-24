---
currentMenu: trigger-swipe
---

# 示例： 在触控设备上通过滑动触发菜单

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<script src='https://cdnjs.cloudflare.com/ajax/libs/jquery.touchswipe/1.6.12/jquery.touchSwipe.min.js'></script>

本示例用到了第三方库 [TouchSwipe](https://github.com/mattbryson/TouchSwipe-Jquery-Plugin)


<span class="context-menu-one btn btn-neutral">在触控设备上滑动</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    // 使得在触控设备上滑动时能打开菜单
    $('.context-menu-one').swipe({
        swipe: function(event, direction, distance, duration, fingerCount) {
            if (fingerCount === 1) {
                $(this).contextMenu({
                    x: event.changedTouches[0].screenX,
                    y: event.changedTouches[0].screenY,
                });
            }
        }
    });

    $.contextMenu({
        selector: '.context-menu-one',
        trigger: 'none',
        callback: function(key, options) {
            var m = "你点击了： " + key;
            window.console && console.log(m) || alert(m);
        },
        items: {
            "edit": {name: "编辑", icon: "edit"},
            "cut": {name: "剪切", icon: "cut"},
            "copy": {name: "复制", icon: "copy"},
            "fold1a": {
                "name": "二级菜单",
                "items": {
                    "fold1a-key1": {"name": "三级菜单 1"},
                    "fold1a-key2": {"name": "三级菜单 2"},
                    "fold1a-key3": {"name": "三级菜单 3"}
                }
            }
        }
    });
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
