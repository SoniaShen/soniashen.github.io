Java中如何终止运行中的线程；while(true){i++;}死循环是如何跳出的:
web link: https://blog.csdn.net/rootkiss/article/details/101596379

[1] omit
[2] omit
[3] omit
[4] 使用volatile标志位:
首先，实现一个Runnable接口，在其中定义volatile标志位，在run()方法中使用标志位控制程序运行。
然后，在main()方法中创建线程，在合适的时候，修改标志位，终止运行中的线程。
最后，运行结果，如下：
