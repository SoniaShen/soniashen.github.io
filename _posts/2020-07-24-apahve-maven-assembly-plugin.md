web link: http://maven.apache.org/plugins/maven-assembly-plugin/
web link: https://stackoverflow.com/questions/45349644/maven-zip-artifact-copy-unzip-and-rename




idea maven zip descriptor


What is an Assembly?
An "assembly" is a group of files, directories, and dependencies that are assembled into an archive format and distributed. For example, assume that a Maven project defines a single JAR artifact that contains both a console application and a Swing application. Such a project could define two "assemblies" that bundle the application with a different set of supporting scripts and dependency sets. One assembly would be the assembly for the console application, and the other assembly could be a Swing application bundled with a slightly different set of dependencies.

The Assembly Plugin provides a descriptor format which allows you to define an arbitrary assembly of files and directories from a project. For example, if your Maven project contains the directory "src/main/bin", you can instruct the Assembly Plugin to copy the contents of this directory to the "bin" directory of an assembly and to change the permissions of the files in the "bin" directory to UNIX mode 755. The parameters for configuring this behavior are supplied to the Assembly Plugin by way of the assembly descriptor.


Something is still missing here.


+-----+-----+-----+-----+

