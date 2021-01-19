web link: https://www.tutorialspoint.com/java/lang/runtime_loadlibrary.htm
web link: https://blog.csdn.net/forandever/article/details/5983846
web link: https://stackoverflow.com/questions/7016391/difference-between-system-load-and-system-loadlibrary-in-java



Description
The java.lang.Runtime.loadLibrary(String filename) method loads the dynamic library with the specified library name. A file containing native code is loaded from the local file system from a place where library files are conventionally obtained. The details of this process are implementation-dependent. The mapping from a library name to a specific filename is done in a system-specific manner.

+-----+-----+-----+-----+-----+

当使用System.loadLibrary()调用 Dll，两种方法:

1.设定环境变量。

比如：所编辑的Dll在目录“D:/cppProjects/nativecode/release”内，将这个路径复制添加到电脑的环境变量中的path变量内即可。

2.设定项目属性。(开发推荐)

右击项目名|选择属性properties|在左边列表内选择“Java Build Path”|在右边选项卡用选择“source”|点开项目名前的“+”号,选择“Native library location”，“Edit”选择上面“D:/cppProjects/nativecode/release”路径。（当然如果将dll拷贝到workspace下也可以用相对路径。也可右击“src”设定其properties内Native Library项。）
————————————————
版权声明：本文为CSDN博主「forandever」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/forandever/java/article/details/5983846





Something is still missing here.


+-----+-----+-----+-----+-----+

Difference between System.load() and System.loadLibrary in Java







How to make JAVA tags?
