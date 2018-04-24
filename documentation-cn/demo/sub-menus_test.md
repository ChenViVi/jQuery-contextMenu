<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [示例： 多级菜单](#demo-submenus)
  - [JavaScript 代码示例](#example-code)
  - [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 示例： 多级菜单

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript代码示例

<script type="text/javascript" class="showcase">$(function(){
    /**************************************************
     * 多级菜单
     **************************************************/
    $.contextMenu({
        selector: '.context-menu-one', 
        callback: function(key, options) {
            var m = "你点击了： " + key;
            window.console && console.log(m) || alert(m); 
        },
        items: {
            "edit": {"name": "编辑", "icon": "edit"},
            "cut": {"name": "剪切", "icon": "cut"},
            "sep1": "---------",
            "quit": {"name": "退出", "icon": "quit"},
            "sep2": "---------",
            "fold1": {
                "name": "一级菜单 1", 
                "items": {
                    "fold1-key1": {"name": "二级菜单 1""},
                    "fold2": {
                        "name": "二级菜单 2", 
                        "items": {
                            "fold2-key1": {"name": "三级菜单 1"},
                            "fold2-key2": {"name": "三级菜单 2"},
                            "fold2-key3": {"name": "三级菜单 3"}
                        }
                    },
                    "fold1-key3": {"name": "二级菜单 3"}
                }
            },
            "fold1a": {
                "name": "一级菜单 2", 
                "items": {
                    "fold1a-key1": {"name": "二级菜单 4"},
                    "fold1a-key2": {"name": "二级菜单 5"},
                    "fold1a-key3": {"name": "二级菜单 6"}
                }
            }
        }
    });
});
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
<div id="msg"></div>
