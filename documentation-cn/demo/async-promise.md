---
currentMenu: async-promise 
---

# 示例： 异步加载菜单项

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript 代码示例](#example-code)
- [HTML 代码示例](#example-html)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<span class="context-menu-one btn btn-neutral">右键点击我</span>

## JavaScript 代码示例

<script type="text/javascript" class="showcase">
    var $ = jQuery;
    $(document).ready(function () {
        'use strict';
        var errorItems = { "errorItem": { name: "加载失败" },};
        var loadItems = function () {
            var dfd = jQuery.Deferred();
            setTimeout(function () {
                dfd.resolve(subItems);
            }, 2000);
            //setTimeout(function () {
            //    dfd.reject(errorItems);
            //}, 1000);
            return dfd.promise();
        };

        var subItems = {
            "sub1": { name: "子菜单 1", icon: "edit" },
            "sub2": { name: "子菜单 2", icon: "cut" },
        };
    
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
                            name: "状态",
                            icon: "delete",
                            items: loadItems(),
                        },
                        "normalSub": {
                            name: "普通的一级子菜单",
                            items: {
                                "normalsub1": { name: "普通的二级子菜单 1"},
                                "normalsub2": { name: "普通的二级子菜单 2"},
                                "normalsub3": { name: "普通的二级子菜单 3"},
                            }
                        }
                    }
                };
            }
        });
    
        //一些异步加载状态用法
        var completedPromise = function (status) {
            console.log(加载完成： ", status);
        };
    
        var failPromise = function (status) {
            console.log("加载失败： ", status);
        };
    
        var notifyPromise = function (status) {
            console.log("加载通知： ", status);
        };
    
        $.loadItemsAsync = function() {
            console.log("异步加载菜单");
            var promise = loadItems();
            $.when(promise).then(completedPromise, failPromise, notifyPromise);
        };
    
    });
</script>

## HTML 代码示例
<div style="display:none;" class="showcase" data-showcase-import=".context-menu-one"></div>
