# Majorsilence Reporting (原名 My-FyiReporting)

如果你要对 Majorsilence Reporting 提一些问题，或者想参与到项目中，这里有一个针对 Majorsilence Reporting 的讨论组：

https://groups.google.com/d/forum/myfyireporting


|         |Linux |Windows |
|---------|:------:|:------:|
|**Release**|NA | [![Build status appveyor](https://ci.appveyor.com/api/projects/status/a44n015bli95rmpw?svg=true)](https://ci.appveyor.com/project/majorsilence/my-fyireporting) |

# 文档
参考 [项目 wiki](https://github.com/majorsilence/My-FyiReporting/wiki).

# 下载

参考 [下载页面](https://github.com/majorsilence/My-FyiReporting/wiki/Downloads).

另外，如果你想跟进最新版本，可以使用 Git

    git clone https://github.com/majorsilence/My-FyiReporting.git

# 介绍
"FYIReporting Designer 是一个基于微软报表定义语言 (RDL) 的报表系统。 
完全支持表格、表单、矩阵、图表，支持 HTML, PDF, XML, .Net 控件, 和打印。 
一个所见即所得设计器使你可以不必了解 RDL 即可创建报表，方便的向导可用于创建新报表，插入表格、矩阵和图表到已存在的报表中。" (http://www.fyireporting.com/)

使用 .NET 报表查看控件即可，ASP.NET、WPF、或者 Winforms 都可以，语言可选择 C#、F#、VB.NET、IronPython 以及其他 .NET 语言。winform 查看器使用mono可以工作在 linux 下。另外，有一个实验性的 Gtk/WPF/Cocoa 查看器。 

Majorsilence Reporting 最初叫 My-FyiReporting，它是 fyiReporting 消亡后的一个分支。它更名为 Majorsilence Reporting 以表示它是项目的一个单独的分支。Majorsilence Reporting 是 fyiReporting 的一个分支。我强调得够多了，这是一个分支。
主要的目的是确保我对 fyiReporting 有一个拷贝，因为那个项目看起来消亡了。I am leaving the
github project named My-FyiReporting so links are not broken. 所有的品牌最终都会被 Majorsilence Reporting 所替代。

另外，检查这个 [项目 wiki](https://github.com/majorsilence/My-FyiReporting/wiki) ，信息会逐渐添加上。

当前，Majorsilence Reporting 使用 visual studio 2010 和 2012 构造，目标平台是 .net 4.0。你也可以执行 Release-Builds 文件夹中的构建脚本来构建 .net 3.5 (可能会出错) 和 4.0 程序包。  

# 开发
Majorsilence Reporting 按以下工作流程开发:

* 好几个星期都没事儿
* 有人需要它做一些现在不会做的事
* 某人实现某些东西并提交一个 pull 请求
* 重复
如果它没有你想要它包含的特性，添加。如果它有一个你需要修复的错误，修复。

## 参与:
欢迎所有的参与.  我会尽量在同一天回答任何电子邮件或 pull 请求，最多几天。最好是小的 pull 请求，因为它们容易复审。

参考 wiki 页面 [https://github.com/majorsilence/My-FyiReporting/wiki/Contribute](https://github.com/majorsilence/My-FyiReporting/wiki/Contribute)

### 核心团队

* [majorsilence](https://github.com/majorsilence) (Peter Gill)
* [Gankov](https://github.com/Gankov)


### 参与者

非常感谢所有 Majorsilence Reporting 的参与者：

* [ausadmin](https://github.com/ausadmin)
* [Geek648](https://github.com/Geek648)
* [kobruleht](https://github.com/kobruleht)
* [jzielke](https://github.com/jzielke)
* [gam6itko](https://github.com/gam6itko)
* [tsliang](https://github.com/tsliang)
* [mohsenalikhani](https://github.com/mohsenalikhani)
* [mgroves](https://github.com/mgroves)
* [sobolev88](https://github.com/sobolev88)


# 结构:

* DataProviders\DataProviders.sln
* Images\
* OracleSp\OracleSp.sln
	* Requires Oracle Data Provider for .NET
* RdlAsp\RdlAsp.sln
	* Asp controls to display reports in asp.net and silverlight pages.
	* References RdlEngine
* RdlCMD\RdlCmd.sln
	* Command line tools
	* References RdlEngine
* RdlCri\RdlCri.sln
	* Custom Report Controls
	* References RdlEngine
* RdlDesign\RdlDesign.sln
	* Is the main graphical drag and drop designer used to create reports.
	* References RdlEngine
	* References RdlViewer
* RdlDesktop\RdlDesktop.sln
	* References RdlEngine
* RdlEngine\RdlEngine.sln
	* Main engine.  Is referenced in many of the other projects
* RdlGtkViewer\RdlGtkViewer.sln
	* A Gtk# (gtk-sharp) viewer
* RdlViewer
	* References RdlEngine
	* Disabled COM interop
* RdlMapFile\RdlMapFile.sln
	 * Map viewer
* RdlTest\RdlTests.sln
	 * Tests
* ReportSever\


 RDL 合规性
报表文件格式说明书可以从微软获得。我相信 fyiReporting 当前最兼容于 RDL 2005。如果你想添加更多特性，参考说明书。

* RDL specifications: [http://msdn.microsoft.com/en-us/library/dd297486%28v=sql.100%29.aspx](http://msdn.microsoft.com/en-us/library/dd297486%28v=sql.100%29.aspx)
* 2005 direct link: [http://download.microsoft.com/download/c/2/0/c2091a26-d7bf-4464-8535-dbc31fb45d3c/rdlNov05.pdf](http://download.microsoft.com/download/c/2/0/c2091a26-d7bf-4464-8535-dbc31fb45d3c/rdlNov05.pdf)
* 2008 direct link: [http://download.microsoft.com/download/6/5/7/6575f1c8-4607-48d2-941d-c69622e11c32/RDL_spec_08.pdf](http://download.microsoft.com/download/6/5/7/6575f1c8-4607-48d2-941d-c69622e11c32/RDL_spec_08.pdf)
* 2008 R2 direct link: [http://download.microsoft.com/download/B/E/1/BE1AABB3-6ED8-4C3C-AF91-448AB733B1AF/Report%20Definition.xps](http://download.microsoft.com/download/B/E/1/BE1AABB3-6ED8-4C3C-AF91-448AB733B1AF/Report%20Definition.xps)

#用户界面教程:
ReportingCloud (另一个分支) 已经制作了一些关于使用设计器以及创建报表的教程。 
[http://sourceforge.net/projects/reportingcloud/files/](http://sourceforge.net/projects/reportingcloud/files/)

我知道，有其他一些分支，但是上次我检查的时候，它们似乎消亡了。fyiReporting 主站点可以在这里 http://www.fyireporting.com/ 找到，在 [http://www.fyireporting.com/helpv4/index.php](http://www.fyireporting.com/helpv4/index.php) 可以找到一些例子。论坛地址是 [http://www.fyireporting.com/forum/index.php](http://www.fyireporting.com/forum/index.php)。 当然，上面我已经说了，多数版块已经消亡.

UPDATE: ReportFU [http://reportfu.org](http://reportfu.org) is alive?  
UPDATE: NReport [http://nreports.codeplex.com/](http://nreports.codeplex.com/) - Looks dead.

