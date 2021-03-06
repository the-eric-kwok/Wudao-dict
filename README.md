# 无道词典

![py](https://img.shields.io/badge/python-3.4.5-green.svg?style=plastic)![plat](https://img.shields.io/badge/Platform-Windows%2FDebian%2FUbuntu%2FCentOS-green.svg?style=plastic)

---

无道词典，是一个简洁优雅的有道词典命令行版本。支持英汉互查的功能，包含释义、词组、例句等有助于学习的内容。

无道词典致力于做最好的命令行词典，随着我们优化排版、显示，增加生词本和补全功能，提供了良好的用户体验，并在不断改进中。

英汉：

![En_Zh Demo](http://obbgthtoc.bkt.clouddn.com/gitScreenshot%20from%202016-09-22%2010-55-23.png)

汉英:

![Zh_En Demo](http://obbgthtoc.bkt.clouddn.com/Screenshot%20from%202016-09-22%2011-04-50.png)

## 功能特性

1. 基础词典(20w英汉查询 + 10w汉英查询 + 网络词库)
2. 词组查询功能(例如直接输入`wd in order to`)
3. 自动补全功能(按Tab自动补全单词，包含1w个最热的词)
3. 生词本(自动把历史记录存为生词本，`wd -h`查看生词本文件位置)


## 安装说明

当你想要提交issue时，首先执行
    
    git clone https://github.com/the-eric-kwok/wudao-dict
    cd ./wudao-dict/wudao-dict
    bash setup.sh #或者如果你在Windows下，那么是 .\setup.bat

来更新到最新版本，再次测试是否还出现问题。

邮箱: erickwok404@gmail.com

issue: [创建新的issue](https://github.com/the-eric-kwok/Wudao-dict/issues)

### Linux 环境

1. 安装环境: 需要python3和bs4, lxml(在线搜索用)
    #### Debian/Ubuntu
    ```
    sudo apt-get install python3 python3-pip
    sudo pip3 install bs4 pyqt5 lxml
    ```
 
    #### OpenSUSE
    ```
    sudo zypper install python3-pip
    sudo pip3 install bs4 lxml pyqt5
    ```
    #### CentOS
    ```
    sudo yum install python34
    sudo yum install python34-pip
    sudo pip3 install bs4 lxml pyqt5
    ```

2.  运行
    ```sh
    git clone https://github.com/the-eric-kwok/wudao-dict
    cd ./wudao-dict/wudao-dict
    bash setup.sh #或者./setup.sh
    ```

    看到出现`Setup Finished!`表明安装成功。如果发生由于移动安装文件不能使用的情况，只需再次运行该脚本即可。

无法clone的，可以下载 https://github.com/the-eric-kwok/Wudao-dict/archive/master.zip ,然后解压安装使用。

**Note: 注意python的版本，只支持python3**

###Windows

下载安装Python：https://www.python.org/ftp/python/3.6.5/python-3.6.5.exe

安装完成后检查自己的环境变量中是否已经存在Python

可以使用Win+R运行cmd，然后输入python回车，如图所示

![](http://ww1.sinaimg.cn/large/b0ea9931gy1fsmnis71d9j20xz0hrdgb.jpg)

OK的话，双击`setup.bat`进行安装

## 使用说明
### 命令行

运行`wd -h`查看使用说明。

```
$ wd -h
Usage: wd [OPTION]... [WORD]
Youdao is wudao, a powerful dict.
-k, --kill             kill the server process            (退出服务进程)
-h, --help             display this help and exit         (查看帮助)
-S, --short-desc       show sentence or not               (只看释义)
-s  --save             save currently querying word       (保存当前正在查询的词)
-a, --auto-save        auto save to notebook or not       (是否自动存入生词本)
-n  --notebook         show notebook                      (输出生词本内容)
-w  --word-count       show word count                    (输出查词计数)
-c  --config           show config                        (查看当前配置)
```

查词时可以直接使用`wd 词语`查汉英词典，或`wd word`查英汉词典(可以自动检测中英文)。

### 图形界面

打开启动器，选择“无道词典”或 Wudao（如果是英文系统的话）
或者在桌面双击启动“无道词典”

![](http://ww1.sinaimg.cn/large/b0ea9931gy1fsmnkerrurj20me0gb3zf.jpg)

![](http://ww1.sinaimg.cn/large/b0ea9931gy1fsmnkm3hfpj20me0gbjs7.jpg)

**现已支持自动补全！！**

![Demo](http://ww1.sinaimg.cn/large/b0ea9931gy1fsohslxsy6g20nb0gjahn.gif)

## 小贴士

0. ./wd_monofile 是本词典的在线查询的单文件版本, 可以复制到`/usr/bin`下直接使用.(需要安装bs4)
1. 如果您不想看到例句, 请使用`wd -S`来开启简略输出.
2. 默认不启用自动存入生词本，如果你想让自己所查的词被自动存入单词本，请使用`wd -a`来开启自动保存.
3. 如果你只想保存一个单词，而不愿开启自动保存，那你可以用`wd -s word`
2. 有的用户反馈字体颜色看不清的问题, 你可以找到./wudao-dict/wudao-dict/src/CommandDraw.py, 可以看到释义,读音等采用的颜色, 直接修改即可.
3. 查询词组直接键入类似`wd take off`即可.

## Release Notes

#### Ver 1.0 (Oct 10, 2016)

* 提供了基础的英汉互查的功能
* 提供了在线查询的功能，并且查过后会缓存

#### Ver 1.1 (Dec 1, 2016)

* 提供了可以单独运行的单文件版本

#### Ver 1.2 (Nov 22, 2017)

* 在线查询修复了不显示被查词的bug

#### Ver 2.0 (Dec 7, 2017)

* 修复了文件夹过大的问题，由263M缩小到80M左右。<a href="https://github.com/ChestnutHeng/Wudao-dict/issues/1"> issue #1: 文件夹大小</a>
* 添加了更多的常用词和单复数形式
* 取消了网络搜索功能，没有在本地找到时会自动进行网络搜索
* 添加了tab补全的支持，对常用的1w词进行tab补全 <a href="https://github.com/ChestnutHeng/Wudao-dict/issues/15">issue #15: 模糊查询的支持</a>
* 添加了生词本功能，自动把查过的词和释义添加到生词本文件中
* 优化了排版，同一单词不再截断换行了 #该功能因为转移字符的问题搁置 <a href="https://github.com/ChestnutHeng/Wudao-dict/issues/16">issue #16:避免在单词内换行</a>

#### Ver 2.1 (May 27, 2018)

* 启用了图形界面

#### Ver 2.2 (Jun 24, 2018)

* 删除了所有系统调用，以增强跨平台可移植性
* 目前已可在 Windows 下运行 GUI（命令行由于彩色显示的问题，默认不启用）

#### Ver 2.3 (Jun 26, 2018)

* GUI 现已可以使用图形界面！
* 给命令行增加了删除生词本内的单词的功能

