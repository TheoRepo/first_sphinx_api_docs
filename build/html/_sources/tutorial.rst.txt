用Sphinx快速制作文档
=======

Sphinx 是一种文档工具, 它可以令人轻松的撰写出清晰且优美的文档, 由 Georg Brandl 在BSD 许可证下开发
新版的Python文档就是由Sphinx生成的,  并且它已成为Python项目首选的文档工具,同时它对 C/C++ 项目也有很好的支持; 并计划对其它开发语言添加特殊支持. 
本站当然也是使用 Sphinx 生成的, 它采用reStructuredText! Sphinx还在继续开发. 下面列出了其良好特性,这些特性在Python官方文档中均有体现:

- **丰富的输出格式**: 支持 HTML (包括 Windows 帮助文档), LaTeX (可以打印PDF版本), manual pages（man 文档）, 纯文本
- **完备的交叉引用**: 语义化的标签,并可以自动化链接函数,类,引文,术语及相似的片段信息
- **明晰的分层结构**: 可以轻松的定义文档树,并自动化链接同级/父级/下级文章
- **美观的自动索引**: 可自动生成美观的模块索引
- **精确的语法高亮**: 基于 Pygments 自动生成语法高亮
- **开放的扩展**: 支持代码块的自动测试,并包含Python模块的自述文档(API docs)等

Sphinx 使用 reStructuredText 作为标记语言, 可以享有 Docutils 为reStructuredText提供的分析, 转换等多种工具.


安装Sphinx
~~~~~~~~~~~~~~~
Sphinx为Python语言的一个第三方库。我们需要在终端中输入下列命令进行安装: 

.. literalinclude:: install.sh
   :lines: 1



创建Sphinx项目
~~~~~~~~~~~~~~~
创建一个用于存放文档的文件夹, 然后在该文件夹路径下运行下列命令快速生成Sphinx项目: 

.. literalinclude:: install.sh
   :lines: 2

接下来会让你选择一些配置: 

1. 设置文档的根路径（回车, 使用默认设置）

.. literalinclude:: interactive.txt
   :lines: 1,2


2. 是否分离source和build目录（输入y,选择分离, 方便管理）

.. literalinclude:: interactive.txt
   :lines: 3,4,5,6

3. 设定模板前缀（回车, 使用默认选项）

.. literalinclude:: interactive.txt
   :lines: 7,8,9,10

4. 输入项目名称和作者

.. literalinclude:: interactive.txt
   :lines: 11,12,13

5. 输入项目版本号

.. literalinclude:: interactive.txt
   :lines: 14,15,16,17,18,19,20

6. 文档语言（回车, 默认即可）

.. literalinclude:: interactive.txt
   :lines: 21,22,23,24,25,26

7. 设定文档文就按的后缀

.. literalinclude:: interactive.txt
   :lines: 27,28,29

8. 设定首页名称（回车, 选择默认index即可）

.. literalinclude:: interactive.txt
   :lines: 30,31,32,33,34

9. 根据需要选择是否开启epub输出(一般用不到, 回车默认不开启即可)

.. literalinclude:: interactive.txt
   :lines: 35,36

10. 根据需求选择是否开启相应的Sphinx拓展功能

.. literalinclude:: interactive.txt
   :lines: 37,38,39,40,41,42,43,44,45,46,47,48,49

11. 创建项目

.. literalinclude:: interactive.txt
   :lines: 50,51,52,53,54,55,56,57,58,59,60,61,62,63


项目创建以后目录结构如下所示:

.. literalinclude:: tree.txt
   :lines: 1,2,3,4,5,6,7,8,9

- build:用来存放通过make html生成文档网页文件的目录
- source: 存放用于生成文档的源文件
- conf.py: Sphinx的配置文件
- index.rst: 主文档

定义文档结构
~~~~~~~~~~~~~~~
主文档index.rst的主要功能是被转换成欢迎页, 它包含一个目录表（ “table of contents tree”或者 toctree ). Sphinx 主要功能是使用 reStructuredText, 把许多文件组织成一份结构合理的文档.

toctree指令初始值如下: 

.. literalinclude:: index.rst
   :lines: 9,10

你可以在 content 的位置添加文档列表:

.. literalinclude:: index.rst
   :lines: 9,10,11,12,13,14

注: 文档文件放在与index.rst同级目录下。

支持markdown文件、更改文档主题
~~~~~~~~~~~~~~~
* Spinx本身不支持.md文件生成文档, 需要我们使用第三方库recommonmark进行转换。 首先分别运行下列命令安装recommonmark与sphinx_rtd_theme库。

.. literalinclude:: install.sh
   :lines: 3,4


安装好, 在conf.py中修改下列两个配置: 

.. literalinclude:: conf.py
   :lines: 57,58

并新增：

.. literalinclude:: conf.py
   :lines: 61,62,63,64


生成文档
~~~~~~~~~~~~~~~
在Sphinx项目所在的文件夹路径下运行下列命令生成文档: 

.. literalinclude:: install.sh
   :lines: 5

生成后的文档位于build/html文件夹内, 用浏览器打开index.html即可看到生成后的文档。





