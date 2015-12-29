这篇主要介绍Eclipse中Checkstyle的配置。关于Checkstyle，引用百度百科的介绍如下：CheckStyle是SourceForge下的一个项目，提供了一个帮助JAVA开发人员遵守某些编码规范的工具。它能够自动化代码规范检查过程，从而使得开发人员从这项重要，但是枯燥的任务中解脱出来。CheckStyle检验的主要内容包括：Javadoc注释、命名约定、标题、Import语句、体积大小、空白、修饰符、块、代码问题、类设计、混合检查。
如果我们想要使用Checkstyle，首先必须在Eclipse中安装Checkstyle插件，关于插件的安装教程网上到处都是，在这里就略过了。下面主要讲一下Checkstyle的配置。具体步骤如下：
1.在Eclipse中打开Windows-->Preferences-->Checkstyle，如下图所示：

![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_checkstyle_preferences.png](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_checkstyle_preferences.png)

通过界面我们可以发现，Checkstyle插件中默认内置有2个执行代码检查的配置文件：Sun Checks、Sun Checks(Eclipse)。这两个配置文件中分别定义了Checkstyle需要检查的选项配置。一般项目组都会根据项目需求自定义一个配置文件，然后通过import的方式导入到Eclipse中。今天，我们主要介绍这一种方式。
2.点击New，在弹出的界面中Type下拉框选择External Configuration File，然后引入我们自定义的配置检查xml文件，Name可以自定义，如下图所示：
![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fexternal_checkstyle_configure.png](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fexternal_checkstyle_configure.png)

点击OK保存，然后我们在前一个界面中就能看到我们刚刚导入的配置了。就是下图中的chenzhou_checkstyle

![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fglobal_check_configurations.png](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fglobal_check_configurations.png)

我们可以鼠标选中该行，然后点击右边的Set as Default按钮，这样Checkstyle就已经配置好了。
 
配置好了Checkstyle，我们还需要单独在项目中激活Checkstyle检查，具体方法为：
右键点击项目-->Properties-->Checkstyle，在弹出的界面中选中Checkstyle active for this project前的复选框，同时在Configure栏选中我们自定义的配置chenzhou_checkstyle，如下图所示
![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fset_checkstyle_default.png](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fset_checkstyle_default.png)

点击OK保存后项目会rebuild，这样Checkstyle检查就已经激活了。
我们可以打开我们的代码，如果代码中有不符合Checkstyle定义的规范的地方，Eclipse会黄色高亮显示，如下图所示：
![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_check_style_show.png](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_check_style_show.png)
如果我们把鼠标悬停在高亮代码上，Eclipse会给出提示警告信息。
对于Checkstyle检查选项的详细配置，我们可以在Eclipse中进行配置修改，如下图，选中chenzhou_checkstyle
![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fglobal_check_configurations_1.png](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fglobal_check_configurations_1.png)

点击右边的Configure按钮，弹出下面的界面
![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_checkstyle_configuration.png](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_checkstyle_configuration.png)

上图中，左边的菜单项代表我们可以进行配置的选项，每一个菜单项都可以展开为多个子菜单项。我们可以分别进行配置。其中菜单项上标了绿色对勾的表示该项以及所有子项已经添加到了检查项中。如果子项没有全部添加，则父菜单项不会显示绿色对勾。
![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_checkstyle_javadoc_comments.png](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_checkstyle_javadoc_comments.png)

如果我们需要添加某个配置项，可以点击选中某个菜单项，然后点击下方的Add按钮，选择OK后该项的子菜单项会显示在右边区域，我们可以通过勾选菜单项前的复选框对具体的项进行配置。如下图所示
![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_checkstyle_known_modules.png](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_checkstyle_known_modules.png)




