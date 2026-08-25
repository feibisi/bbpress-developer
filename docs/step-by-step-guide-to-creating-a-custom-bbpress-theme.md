---
title: "创建自定义 bbPress 主题的分步指南"
post_status: publish
post_name: step-by-step-guide-to-creating-a-custom-bbpress-theme
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-theme]
source:
  blog_id: 4
  post_id: 57
  guid: "http://import.local/2021/12/24/step-by-step-guide-to-creating-a-custom-bbpress-theme/"
---

**以下内容是为 bbPress WordPress 插件的 2.2 版编写的。本教程中的信息可能不适用于插件的早期或后续版本。考虑到这一点，进入教程！**

### [第 1 步：安装 WordPress](#step-1-install-wordpress)

过去，bbPress 是一个独立的论坛脚本，如果您稍微修改一下它，它就可以与 WordPress 一起使用，但现在情况不再如此，并且任何说明如此多的信息都已过时。如今，bbPress 是[WordPress](http://www.wordpress.org)的一个插件，它本身无法工作。所以，如果您还没有，[您需要在您的网络服务器上安装 WordPress](https://codex.wordpress.org/Installing_WordPress)，bbPress 才能正常工作。

### [第 2 步：安装 bbPress](#step-2-install-bbpress)

设置好 WordPress 后，安装插件就很容易了。（但是，如果您仍然需要帮助，可以按照[本指南进行操作](https://codex.wordpress.org/Plugins_Add_New_Screen)！）在管理面板的插件区域中，搜索bbPress插件；将会出现几个，但很明显哪个是核心 bbPress 插件。安装并启用 bbPress 插件。如果您找不到它，那就是[这个](https://wordpress.org/plugins/bbpress/)。

### [第 3 步：编辑 bbPress 的设置](#step-3-edit-bbpress-settings)

安装并启用 bbPress 插件后，您的 WordPress 管理侧边栏底部将出现三个新菜单选项：
![](/_images/Screenshot2021-12-25-16.45.04.webp)
您还将拥有两个新的子菜单选项：工具 > 重新计数和设置 > 论坛。
既然您知道所有内容都在哪里，请单击“设置”下的“论坛”。该区域将帮助您控制 bbPress 插件的基本特性和功能。花一点时间将设置更改为您希望的设置。
请注意，此区域不包含用于编辑主题布局或样式的方法。这将在随后的 bbPress 版本中略有改变，但目前情况确实如此。

### [第 4 步：创建一些论坛](#step-4-make-some-forums)

转至论坛>新论坛并添加详细信息以创建新论坛。您可以根据需要创建任意数量的论坛，或者如果愿意，可以通过管理区域创建主题、回复和标签。已经制作了其中的一些内容可能会帮助您以后更彻底地测试您的设计。

### [第 5 步：创建子主题](#step-5-create-a-child-theme)

如果您正在运行默认的[二十](https://wordpress.org/extend/themes/twentyten)或[二十一](https://wordpress.org/extend/themes/twentyeleven)主题的bbPress应该工作还算不错的开箱。但是，您可能没有运行这些主题，或者至少不打算无限期地运行它们，因此您会想知道如何自定义 bbPress。这就是 WordPress 的一个功能“子主题”变得有用的地方。
转到 WordPress Codex 并[按照](https://codex.wordpress.org/Child_Themes)有关如何创建和启用子主题的说明进行操作（或者，[本指南](http://op111.net/53/)提供了更多详细信息）。对于此步骤和下一步，您需要使用 FTP 客户端（[此处为 FTP 说明](https://codex.wordpress.org/FTP_Clients)）。
子主题允许您同时运行两个连接的主题。在 bbPress 和 WordPress 一起工作的情况下，一个（可能是父级）将包含您的 WordPress 设计文件，而另一个（可能是子级）将包含您的 bbPress 设计文件。子级将尽可能多地继承父级的风格品质；您需要添加到子项的任何其他内容都将在其自己的文件夹中完成。

#### [故障排除提示](#troubleshooting-tip)

如果您在让 WordPress 识别您的子主题时遇到问题，请确保在您的父/WordPress 主题的 header.php. 它应该是这样的：

### [第 6 步：将默认 bbPress 主题复制到您的子主题文件夹](#step-6-copy-the-default-bbpress-theme-to-your-child-theme-folder)

默认文件不再存储在wp-content > plugins > bbpress > bbp-themes 中。在bbpress > templates > default 中有一个名为 default 的文件夹  ，但我不知道哪些文件需要复制。
仍在 FTP 中并查看WordPress 安装的根文件夹时，转到 bbPress 的主题文件夹。也就是说，转到wp-content > plugins > bbpress > bbp-themes > bbp-twentyten。从此文件夹下载所有文件，除了style.css. 这些文件将为您的 bbPress 主题设置样式。
现在返回到您的子主题文件夹（wp-content > themes > yourthemefolder-child）。将默认的 bbPress 主题文件上传到子主题文件夹。您可以通过将新screenshot.png图像上传到此文件夹来更改您在管理区域中看到的子主题图像。

### [第 5 步：自定义 bbPress 的主题文件](#step-5-customize-the-bbpress-theme-files)

准备好所有文件后，您现在可以开始设计所有内容。当然，CSS 对您的论坛的视觉样式有很大帮助，但在某些情况下，您也需要编辑布局。为此，请找到相关文件，在文本编辑器中对其进行编辑（[Notepad++](http://notepad-plus-plus.org/)很好用），使用 FTP 客户端覆盖旧文件，然后进行测试。CTRL+Z 可能是也可能不是您的朋友。
有时可能会混淆哪个文件控制什么。请注意，每当您bbp\_get\_template\_part在 bbPress 模板中看到时，它都会从另一个文件（通常与其引用的任何函数的名称相似）中提取模板信息。您可能需要进行一些挖掘才能找到要编辑的正确文件，但它们的名称和结构都很好，因此不应该花费太多精力。
现在，获取主题！如果您有任何疑问，[请访问支持论坛](https://bbpress.org/forums/)。
