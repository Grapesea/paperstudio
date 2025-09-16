## Git环境安装

### 软件安装

首先安装Git bash（针对Windows系统）：[Git - Downloading Package](https://git-scm.com/downloads/win)

安装一个可以提供Git功能的IDE，常用的是Visual Studio Code（即VSCode）：[Visual Studio Code - Code Editing. Redefined](https://code.visualstudio.com/)

### 配置Git环境

Windows系统中：打开cmd或者windows自带的powershell；

配置全局用户名：

```bash
git config --global user.name "你的用户名"
```

配置全局邮箱：

```bash
git config --global user.email "你的邮箱@example.com"
```

此时为了验证配置成功，可以使用指令：

```bash
git config --list
```

效果图示例：

<center><img src="../figures/3.png" style="zoom: 40%;" /></center>

!!! tips

    cmd打开方式：键盘上按住`Win+R`，打开窗口中输入cmd并确定即可；
        
    <center><img src="../figures/1.png" style="zoom: 50%;" /></center>
        
    powershell打开方式：键盘上按住`Win`，在搜索框中输入`powershell`并打开对应界面；
        
    <center><img src="../figures/2.png" style="zoom: 40%;" /></center>

### 在VSCode中配置Git

VSCode通常会自动检测Git，你也可以：

打开VSCode设置（Ctrl + ,），搜索"git.path"。如果需要，手动指定Git路径（默认是 `C:\Program Files\Git\bin\git.exe`）

### Clash for Windows的安装



## Git Clone：将文档文件夹所有内容放置到自己的电脑中

本站点GitHub仓库是https://github.com/grapesea/paperstudio，你可以在电脑的某个空间足够的磁盘中（如E盘）输入以下命令来克隆：

```bash
PS E:\> git clone https://github.com/grapesea/paperstudio
```

如果只想要最近的1次git记录，可以：

```bash
PS E:\> git clone --depth 1 https://github.com/grapesea/paperstudio
```

这样你的E盘中就出现paperstudio这个文件夹了！

## 本地预览

首先切换到项目文件夹中，我把paperstudio文件夹存到了`E:\paperstudio`这个地址内（以下全部以这个文件夹为例），那么：

```bash
PS C:\Users> cd E:      //第二行是输入第一行内容后按enter后出现的
PS E:\> cd paperstudio  //第三行是输入第二行内容后按enter后出现的
PS E:\paperstudio>
```

在Python环境已经具备的情况下，安装mkdocs：

```bash
PS E:\paperstudio> pip install mkdocs
```

查看帮助文档：

```bash
PS E:\paperstudio> mkdocs serve -h
```

此时跳出以下说明：

```bash
Usage: mkdocs serve [OPTIONS]

  Run the builtin development server.

Options:
  -a, --dev-addr <IP:PORT>        IP address and port to serve documentation locally (default: localhost:8000)
  -o, --open                      Open the website in a Web browser after the initial build finishes.
  --no-livereload                 Disable the live reloading in the development server.
  --dirty                         Only re-build files that have changed.
  -c, --clean                     Build the site without any effects of `mkdocs serve` - pure `mkdocs build`, then
                                  serve.
  --watch-theme                   Include the theme in list of files to watch for live reloading. Ignored when live
                                  reload is not used.
  -w, --watch PATH                A directory or file to watch for live reloading. Can be supplied multiple times.
  -f, --config-file FILENAME      Provide a specific MkDocs config. This can be a file name, or '-' to read from
                                  stdin.
  -s, --strict / --no-strict      Enable strict mode. This will cause MkDocs to abort the build on any warnings.
  -t, --theme [material|mkdocs|readthedocs]
                                  The theme to use when building your documentation.
  --use-directory-urls / --no-directory-urls
                                  Use directory URLs when building pages (the default).
  -q, --quiet                     Silence warnings
  -v, --verbose                   Enable verbose output
  -h, --help                      Show this message and exit.
```

所以想要实时预览只需要输入以下命令即可：

```bash
PS E:\paperstudio> mkdocs serve
```

如果有多个mkdocs文档同时需要预览，可以更改ip和端口号，如：

```bash
PS E:\paperstudio> mkdocs serve -a 127.0.0.1:7000
```

如果出现以下内容，就可以在浏览器的地址栏中输入`127.0.0.1:7000`或者`localhost:7000`（因为localhost默认ip地址就是`127.0.0.1`）进行实时预览了：

```bash
PS E:\paperstudio> mkdocs serve -a 127.0.0.1:7000
INFO    -  Building documentation...
INFO    -  Cleaning site directory
INFO    -  Documentation built in 0.39 seconds
INFO    -  [17:50:01] Serving on http://127.0.0.1:7000/paperstudio/
```