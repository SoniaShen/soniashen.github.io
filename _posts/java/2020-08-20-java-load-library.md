How to Load a Java Native/Dynamic Library (DLL):
web link: https://www.chilkatsoft.com/java-loadLibrary-Windows.asp

i.e. Specify the java.library.path on the command line by using the -D option:
  $ java -Djava.library.path=c:\chilkatJava TestApp

 =====> =====> =====> =====> =====> 

Unit test Java class that loads native library:
web link: https://stackoverflow.com/questions/34802667/unit-test-java-class-that-loads-native-library

i.e. Just make sure, the directory containing the library is contained in the java.library.path system property.
From the test you could set it before you load the library:
  System.setProperty("java.library.path", "... path to the library .../libs/x86");

You can specify the path hard coded, but this will make the project less portable to other environments. So I suggest you build it up programmatically.

 =====> =====> =====> =====> =====>

How do I load and use native library in java?
web link: https://stackoverflow.com/questions/11783632/how-do-i-load-and-use-native-library-in-java

i.e. Do the following:
[1] Use System.loadLibrary("mylib");
[2] Copy mylib.so to libmylib.so
[3] Run java -Djava.library.path=/root/ Main


 =====> =====> =====> =====> =====>

maven-surefire-plugin, DLLs and java.library.path
web link: https://stackoverflow.com/questions/15199768/maven-surefire-plugin-dlls-and-java-library-path

i.e. 1 Answer
Your <argLine/> points to an incorrect path. Try this instead:

<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <configuration>
        <forkMode>once</forkMode>
        <workingDirectory>target</workingDirectory>
        <argLine>-Djava.library.path=${basedir}/src/main/resources/lib</argLine>
    </configuration>
</plugin>

If this DLL will only be used for tests, you should put it under src/test/resources. In that case the <argLine/> path will change to ${project.build.directory}/test-classes.


 =====> =====> =====> =====> =====>

java.lang.UnsatisfiedLinkError no *****.dll in java.library.path
web link: https://stackoverflow.com/questions/1403788/java-lang-unsatisfiedlinkerror-no-dll-in-java-library-path
i.e. Answer: [suggested]
 If you set the system property java.library.path to the directory where your DLL is located, then System.loadLibrary will indeed find your DLL. However, if your DLL in turn depends on other DLLs, as is often the case, then java.library.path cannot help, because the loading of the dependent DLLs is managed entirely by the operating system, which knows nothing of java.library.path. 







