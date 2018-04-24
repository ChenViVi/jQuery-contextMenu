---
currentMenu: sub-menus-promise  
---

# 示例： 异步加载子菜单

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
var errorItems = { "errorItem": { name: "无法加载项目" }};//example usage if you want to reject promise
    var loadItems = function () {//example method that will eventually do an async call
        var dfd = jQuery.Deferred();
        setTimeout(function () {
            dfd.resolve(subItems);
        }, 1000);
        //setTimeout(function () {
        //    dfd.reject(errorItems);
        //}, 1000); //could be used to reject items, providing the same format list.
        return dfd.promise();//返回 jquery promise对象, 请查看 https://www.jquery123.com/deferred.promise/
    };

    var subItems = {
        "sub1": { name: "二级菜单 1", icon: "edit" },
        "sub2": { name: "二级菜单 2", icon: "cut" },
    };
    //normal context menu initialization.
    $.contextMenu({
        selector: '.context-menu-one',
        build: function ($trigger, e) {
            return {
                callback: function (key, options) {
                    var m = "你点击了： " + key;
                    console.log(m);
                },
                items: {
                    "edit": { name: "编辑", icon: "edit" },
                    "cut": { name: "剪切", icon: "cut" },
                    "status": {
                        name: "Status",
                        icon: "delete",
                        items: loadItems(),//返回一个promise对象而不是子菜单项
                    },
                }
            };
        }
    });
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
