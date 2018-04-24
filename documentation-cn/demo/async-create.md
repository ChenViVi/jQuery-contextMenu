---
currentMenu: async-create
---

# 示例： 异步加载菜单

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    // 异步创建菜单
    function createSomeMenu() {
        return {
            callback: function(key, options) {
                var m = "你点击了：" + key;
                window.console && console.log(m) || alert(m);
            },
            items: {
                "edit": {name: "编辑", icon: "edit"},
                "cut": {name: "剪切", icon: "cut"},
                "copy": {name: "复制", icon: "copy"}
            }
        };
    }

    // 处理异步加载菜单点击事件
    $('.context-menu-one').on('mouseup', function(e){
        var $this = $(this);
        // store a callback on the trigger将回调方法保存到触发器
        $this.data('runCallbackThingie', createSomeMenu);
        var _offset = $this.offset(),
            position = {
                x: _offset.left + 10,
                y: _offset.top + 10
            }
        // 异步打开菜单
        setTimeout(function(){ $this.contextMenu(position); }, 1000);
    });

    // 设置菜单
    $.contextMenu({
        selector: '.context-menu-one',
        trigger: 'none',
        build: function($trigger, e) {
            e.preventDefault();

            // 从触发器中取出回调方法
            return $trigger.data('runCallbackThingie')();
        }
    });
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
