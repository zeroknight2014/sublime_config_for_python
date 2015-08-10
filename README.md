# sublime_config_for_python
sublime的python开发环境配置

1.安装sublime3，按" Ctrl+ ` "安装package control插件(具体安装方法看这里https://packagecontrol.io/installation);

2.安装其他插件：
    *tomorrow Color Theme，选择preferences中的Color Scheme的Tomorrow Color Scheme中的Tomorror-Night配色主题，这是一个非常酷的暗黑系样式。
    *Theme - Soda Dark  ，Themes 影响 Sublime 界面元素的颜色和风格。这个非常适合 Tomorrow Night 的配色方案。
    *SideBarEnhancements 这个插件提供了侧边栏附加的上下文菜单选项，例如"New file"，"New Floder"等。
    *SublimeCodeIntel 为部分语言增强自动完成功能，包括了 Python 。这个插件同时也可以让你跳转到符号定义的地方，通过按住 alt 并点击符号。非常方便。不过体积很大，要下载很久。
    *SublimeREPL 允许你在编辑界面直接运行 Python 解释器。
    *GitGutter 在编辑器的凹槽区，依照 Git ，增加小图标来标识一行是否被插入、修改或删除。在 GitGutter 的 readme 中有说明如何更改颜色图标来更新你的配色方案文件。
    *pythonPeP8Format 用于格式化python代码

3.根据自己的喜好配置开发环境。Sublime Text 的优点就是它的所有配置都是简单的基于 JSON 的配置文件。Preferences.sublime-settings 配置了 Sublimede 的显示和行为，你可以在sublime 中通过 Preferences > Settings — User 打开并编辑此文件。Default (Windows).sublime-keymap中可以定义自己喜欢的快捷键方式，你可以在sublime 中通过 Preferences > Key Bindings — User 打开并编辑此文件。

PS：
sublime中运行python可以直接使用ctrl+b，但是如果代码运行中如果需要对外接收参数，如用input等接收输入，此时直接运行会报错：
EOFError: EOF when reading a line
解决办法：安装SublimeREPL后，在perferences中的key binding user中添加如下配置后，使用ctrl+r后即可正常运行代码并接收输入参数：
[
    {"keys":["ctrl+r"] ,
    "caption": "SublimeREPL: Python - RUN current file",
    "command": "run_existing_window_command",
    "args":
        {
            "id": "repl_python_run",
            "file": "config/Python/Main.sublime-menu"
        }
    },
]
