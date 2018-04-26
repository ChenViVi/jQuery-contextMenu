---
currentMenu: introduction
---

# [jQuery contextMenu](https://github.com/swisnl/jQuery-contextMenu)

## Contextmenu plugin & polyfill

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [特点](#features)
- [作者](#authors)
- [许可证](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

The contextMenu Plugin 适用于需要在大量对象上使用菜单的 Web 应用程序。它的实现原理不同于 [a beautiful site's](http://abeautifulsite.net/blog/2008/09/jquery-context-menu-plugin/) 和 [trendskitchens'](http://www.trendskitchens.co.nz/jquery/contextmenu/) 。这个插件把菜单当作是一个对象，而这个菜单对象是唯一的，却被多个对象所使用。 和上面提到的插件不一样, contextMenu 不需要绑定到触发它的对象上。所以当你增加或移除多触发器的时候，不需要重新初始化或者更新 contextMenu。

![context menu rendered by $.contextMenu](screenshots/jquery-contextMenu.subs.png) 

你可以在 contextMenu 中放一些可以点击的选项，或者放一个表单，简单修改一些属性就可以实现。参见： [带表单的菜单](demo/input.html)

一旦注册了一个菜单，它就不能被修改了。 那意味着不能往这个菜单里面添加选项或者移除选项。 contextMenu在内存里面只定义了一次，但却被很多触发对象调用。
我们可以通过 _show_ 回调函数和 _hide_ 回调函数来更新菜单选项的状态。这使得你可以使某些菜单项不可用，可以改变它们的图标，如果菜单项里面有`<input>`元素，你还可以改变`<input>`里面的值。

在版本1.5中，可以动态创建菜单。也就是说，我们之前说的（一旦创建，不能更改）仍然适用，但可以规避。菜单可以动态加载，它们可以根据触发元素而有所不同。

## 特点

*   可以通过右击, [左击](demo/trigger-left-click.html), [悬浮 ](demo/trigger-hover.html)或 [自定义触发事件](demo/trigger-custom.html) 来显示菜单
*   使用事件监听处理器使得触发菜单的对象被 [新增 / 移除 ](demo/dynamic.html) 后不需要重新初始化
*   [动态加载菜单](demo/dynamic-create.html)
*   每个菜单选项可以添加自定义图标（可选）
*   [带表单的菜单](demo/input.html) (text, textarea, checkbox, radio, select)
*   自定义html元素
*   可以在show回调函数和hide回调函数中更新菜单选项的状态
*   即使有数百个触发对象，内存占用也很小
*   调整菜单位置以适应窗口大小
*   [启用 / 禁用](demo/disabled-changing.html) 菜单里面的选项
*   嵌套的 [多级菜单](demo/sub-menus.html)
*   全键盘交互
*   支持[HTML5 `<menu>`](demo/html5-import.html)
*   适用 CSS 来定义菜单的样式

## 作者

*   [Björn Brala (SWIS)](http://www.swis.nl/over-ons/bjorn-brala)
*   [Rodney Rehm](http://rodneyrehm.de/en/)
*   [Christian Baartse](https://github.com/christiaan) (每个菜单都有个单一回调函数)
*   [Addy Osmani](https://github.com/addyosmani) (与Firefox 8中的原生上下文菜单兼容)

## 许可证

$.contextMenu 的许可证是 [MIT](http://www.opensource.org/licenses/mit-license)。
