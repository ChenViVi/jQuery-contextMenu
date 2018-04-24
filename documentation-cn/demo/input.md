---
currentMenu: input 
---

# 示例： 带表单的菜单

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
$(function(){
    $.contextMenu({
        selector: '.context-menu-one', 
        items: {
            // <input type="text">
            name: {
                name: "文本框", 
                type: 'text', 
                value: "Hello World", 
                events: {
                    keyup: function(e) {
                        // 在这里增加一些键盘按键抬起时的处理操作
                        window.console && console.log('key: '+ e.keyCode); 
                    }
                }
            },
            sep1: "---------",
            // <input type="checkbox">
            yesno: {
                name: "Boolean", 
                type: '复选框', 
                selected: true
            },
            sep2: "---------",
            // <input type="radio">
            radio1: {
                name: "单选框 1", 
                type: 'radio', 
                radio: 'radio', 
                value: '1'
            },
            radio2: {
                name: "单选框 2", 
                type: 'radio', 
                radio: 'radio', 
                value: '2', 
                selected: true
            },
            radio3: {
                name: "单选框 3", 
                type: 'radio', 
                radio: 'radio', 
                value: '3'
            },
            radio4: {
                name: "单选框 4", 
                type: 'radio', 
                radio: 'radio', 
                value: '4', 
                disabled: true
            },
            sep3: "---------",
            // <select>
            select: {
                name: "下拉列表", 
                type: 'select', 
                options: {1: 'one', 2: 'two', 3: 'three'}, 
                selected: 2
            },
            // <textarea>
            area1: {
                name: "带高度参数的文本域", 
                type: 'textarea', 
                value: "Hello World", 
                height: 40
            },
            area2: {
                name: "文本域", 
                type: 'textarea', 
                value: "Hello World"
            },
            sep4: "---------",
            key: {
                name: "按钮", 
                callback: $.noop
            }
        }, 
        events: {
            show: function(opt) {
                // $this变量是触发事件的元素
                var $this = this;
                // import states from data store 从数据导入中已保存的内容
                $.contextMenu.setInputValues(opt, $this.data());
                // 这通常会将对象中储存的表单信息填充到表单中
                // 就像： {name: "foo", yesno: true, radio: "3", …}
            }, 
            hide: function(opt) {
                // $this变量是触发事件的元素
                var $this = this;
                // export states to data store
                $.contextMenu.getInputValues(opt, $this.data());将现有输入导出到数据中
                // 这通常会将表单中的数据储存到对象中
                // 就像： {name: "foo", yesno: true, radio: "3", …}
            }
        }
    });
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>