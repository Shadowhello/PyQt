# 多页面

## [1、QScrollArea](QScrollArea/)

[1、仿QQ设置面板](QScrollArea/仿QQ设置面板)

1. 左侧为`QListWidget`，右侧使用`QScrollArea`设置`QVBoxLayout`，然后依次往里面添加QWidget
2. 右侧添加`QWidget`的时候有两种方案
    1. 左侧list根据序号来索引，右侧添加widget时给定带序号的变量名，如widget_0,widget_1,widget_2之类的，这样可以直接根据`QListWidget`的序号关联起来
    2. 左侧list添加item时给定右侧对应的widget变量值

相关事件：
1. 绑定左侧`QListWidget`的`itemClicked`的到该item的索引
2. 绑定右侧滚动条的`valueChanged`事件得到pos

注意：当`itemClicked`时定位滚动条的值时，需要设置一个标志位用来避免`valueChanged`重复调用item的定位

![截图](QScrollArea/仿QQ设置面板/ScreenShot/仿QQ设置面板.gif)

## [2、QStackedWidget](QStackedWidget/)

[1、左侧选项卡](QStackedWidget/左侧选项卡)

本来使用QTabWidget可以实现多标签页面，但是当标签在左侧时会出现文字方向不对的问题，可以通过自定义`QTabBar`来解决，也可以采用QListWidget结合QStackedWidget的方式。

1. 左侧为`QListWidget`，右侧使用`QStackedWidget`，然后依次往里面添加QWidget
2. 右侧添加`QWidget`的时候有两种方案
    1. 左侧list根据序号来索引，右侧添加widget时给定带序号的变量名，如widget_0,widget_1,widget_2之类的，这样可以直接根据`QListWidget`的序号关联起来
    2. 左侧list添加item时给定右侧对应的widget变量值

![截图](QStackedWidget/左侧选项卡/ScreenShot/左侧选项卡.gif)