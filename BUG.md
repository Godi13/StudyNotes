# 生活中遇到的<small><small><small><small><small>小</small></small></small></small></small>BUG汇总

### 1. MarkDown 插件 OmniMarkupPreviewer

Ubuntu系统下，按 <kbd>CTRL</kbd><kbd>ALT</kbd><kbd>O</kbd> 组合键准备预览，结果浏览器弹出`The requested URL could not be retrieved`

```
The following error was encountered while trying to retrieve the URL: http://127.0.0.1:51004/view/55

Connection to 127.0.0.1 failed.

The system returned: (111) Connection refused

The remote host or network may be down. Please try the request again.

Your cache administrator is webmaster.
```

将 _Setting-Default_ 中的 `"server_host": "127.0.0.1"` 改为 `"server_host": "localhost"` 即可

### 2. SublimeText 的 Package Control

<kbd>CTRL</kbd><kbd>SHIFT</kbd><kbd>P</kbd> 输入Package Control却没有，但插件可以正常使用。

```
"ignored_packages":
  [
    "Vintage",
    "Package Control"
  ],

原因：在Preferences.sublime-settings的ignored_packages中，莫名其妙多了"Package Control"
```

### 3. MarkDown CSS代码块

          ```css                 ```sass
    使用           有显示BUG，写成           即可
          ```                    ```

### 4. Ubuntu 任务栏按 <kbd>Windows</kbd> 键出不来

检查键盘上的 __*锁锁锁*__ <kbd>Windows</kbd> __键__ 是否被按下
