# MIT Linear Algebra 18.06 Notes

## 0. 使用方法

直接 git clone 就完事儿了。
所有 Markdown 文件都已经在提交前，按照下述有关设置要求打开并确认一切正常。
除此之外还推荐用 vscode 打开。无论是直接通过 **Markdown Preview**，还是 **vscode-pdf**。

## 1. 对这门课的看法

首先，虽然还没有看完，但是还是要对 Gilbert Strang 教授表示最崇高的敬意。
教授的教学由浅入深，可以说针对的人群十分的广。
我是在 2019 年 2 月开始接触这一系列教学视频的。

* 那个时候的我甚至连矩阵都不知道，教授能够给我对线代的印象。
* 上学期在上线代，在学期中，教授给了我另外一个角度看待平时作业中的问题。
* 对于像我这种刚刚在学校里学完线代课程的普通大学生，可以在更为“线性代数”(adj.)的思想回顾之前学习的公式。
* 对于在数学上已经有很好理解的学生（但很明显不是我），我相信教授一定可以做到线代应用方面的启发。

## 2. 关于 Github 对 Mathjax 的支持

我认为应该是一点都不支持的。
上传到 Github 上的 md 文件，如果在网页中直接打开，对于其中原本应该显示出来的数学公式就会原封不动得到源代码。
所以，如果想要在 浏览器 上直接查看 md 文件，应该是要自己装载 Mathjax 插件。

这里有 Chrome 浏览器 Mathjax 扩展的下载地址：

[Github-Mathjax下载地址](https://github.com/orsharir/github-mathjax/releases)

（注：由于是 release 里面的东西，所以大陆用户下载要**科学上网**。）

**下好了之后，插件如果没有正常自动安装，那么 Win10 八成可以在如下文件夹找到**：

```rm
C:\Users\Username\AppData\Local\Google\Chrome\User Data\Default\Extensions
```

（其他的不知道）

然后在 ```chrome://extensions/``` 中点击 **加载已下载的扩展程序** 就行。

## 3. 之后的问题

### i. Mathjax 也无能为力之处

即使是拥有了浏览器对 Mathjax 的支持，也无法做到解析全部 md 中的 tex 语法。
比如：**矩阵换行符**
原本多行矩阵由于 '\\\\' 最后解析成 一个 '\' 的缘故，所有矩阵看起来都是行向量，而且本应该换行的地方变得很窄，就像只有一个空格那样……

但是相信 git clone 之后得到的不会再是那样。

### ii. typora 无法解析单 '$' 语法

typora 默认情况下只能够支持 '$$' 语法，对于单个 '$' 的行内公式并不支持。

所以需要修改一下设置：

1. 点击 “文件” -> "偏好设置"
2. 点击 “markdown” 选项
3. 将 “Markdown 扩展语法” 下的 “内联公式” 前的方框**打勾**。
4. 保存配置后，重启 typora

这样再次打开后就可以看到行内公式的解析了。

### iii. 图片无法加载的情况

这个问题的表象应该也是因为没有科学上网。
具体解决办法网上搜得到，但是搬运一下：

对于 **Win10** 而言，到这个路径去：

```rm
C:\Windows\System32\drivers\etc
```

寻找一个 host 文件。
在其中追加以下文本：

```rm
# GitHub Start
192.30.253.112    github.com
192.30.253.119    gist.github.com
151.101.184.133    assets-cdn.github.com
151.101.184.133    raw.githubusercontent.com
151.101.184.133    gist.githubusercontent.com
151.101.184.133    cloud.githubusercontent.com
151.101.184.133    camo.githubusercontent.com
151.101.184.133    avatars0.githubusercontent.com
151.101.184.133    avatars1.githubusercontent.com
151.101.184.133    avatars2.githubusercontent.com
151.101.184.133    avatars3.githubusercontent.com
151.101.184.133    avatars4.githubusercontent.com
151.101.184.133    avatars5.githubusercontent.com
151.101.184.133    avatars6.githubusercontent.com
151.101.184.133    avatars7.githubusercontent.com
151.101.184.133    avatars8.githubusercontent.com
# GitHub End
```

如果遇到权限问题，那么修改权限即可。
~~（还看到一位爷，直接拖到另外位置，在修改时将原 host 文件拖回原目录。这样，保存文件时仍保留原 host 文件的一切属性。）~~

## 4. 写作方式

* 采用 vscode 中插件 **Markdown Preview** 提供的方式进行即时预览。
* 并且遵守插件 **markdownlint** 的要求进行较为严格的书写。
* 通过插件 **Markdown PDF** 将 md 文件转为 pdf 文件。

所以相信只要使用 vscode 打开，并 ctrl + k, v 后预览，就可以看到原模原样的 md 文件了。
或者说直接使用 typora 打开，在修改完（3.ii.）中的配置后应该也是可以的。
