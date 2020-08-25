Final static variable in Java:
web link: https://www.geeksforgeeks.org/final-static-variable-java/

i.e. static:
Whenever we declare variable as static, then at the class level a single variable is created which is shared with the objects. Any change in that static variable reflect to the other objects operations. If we won’t initialize a static variable, then by default JVM will provide a default value for static variable.

i.e. final:
But when we declare a static variable with final modifier then we should take care of the following conventions:
[1] Declaring variables only as static can lead to change in their values by one or more instances of a class in which it is declared.
[2] Declaring them as static final will help you to create a CONSTANT. Only one copy of variable exists which can’t be reinitialize.

 ====> ====> ====> ====> ====>

Java Final arraylist:
web link: https://stackoverflow.com/questions/4525642/java-final-arraylist

i.e.   private static final ArrayList list = new ArrayList(); 
[1] private Means only this class (SomeClass) can access list
[2] static Means that there is only one instance of the list variable for all instances of SomeClass to share. The list instance is associated with the SomeClass class rather than each new SomeClass instance. If a variable is non-static it's said to be an instance variable
[3] final as you know means that you cannot reassign the list variable another value.

i.e. ArrayList list = new ArrayList();
[1] In the second declaration there are no modifiers, so the variable is an instance variable and it also gets package-private access protection (Sometimes called default access protection). This means that this class (SomeClass) and other classes in the same package can access the variable.
[2] You can find out more about public, private, and package-private here: Access control
[3] You can find out more about final and static here: Class variables

i.e. Access control:
web link: http://download.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html

i.e. Class variables:
web link: http://download.oracle.com/javase/tutorial/java/javaOO/classvars.html

 ====> ====> ====> ====> ====>

Java final修饰符详解:
web link: http://c.biancheng.net/view/6053.html

i.e. 使用 final 关键字声明类、变量和方法需要注意以下几点：
[1] final 用在变量的前面表示变量的值不可以改变，此时该变量可以被称为常量。
[2]final 用在方法的前面表示方法不可以被重写（子类中如果创建了一个与父类中相同名称、相同返回值类型、相同参数列表的方法，只是方法体中的实现不同，以实现不同于父类的功能，这种方式被称为方法重写，又称为方法覆盖。这里了解即可，教程后面我们会详细讲解）。
[3] final 用在类的前面表示该类不能有子类，即该类不可以被继承。

i.e. final 修饰基本类型变量和引用类型变量的区别:
[1] 当使用 final 修饰基本类型变量时，不能对基本类型变量重新赋值，因此基本类型变量不能被改变。 但对于引用类型变量而言，它保存的仅仅是一个引用，final 只保证这个引用类型变量所引用的地址不会改变，即一直引用同一个对象，但这个对象完全可以发生改变。
[2] 从上面程序中可以看出，使用 final 修饰的引用类型变量不能被重新赋值，但可以改变引用类型变量所引用对象的内容。例如上面 iArr 变量所引用的数组对象，final 修饰后的 iArr 变量不能被重新赋值，但 iArr 所引用数组的数组元素可以被改变。与此类似的是，p 变量也使用了 final 修饰，表明 p 变量不能被重新赋值，但 p 变量所引用 Person 对象的成员变量的值可以被改变。
[3] 注意：在使用 final 声明变量时，要求全部的字母大写，如 SEX，这点在开发中是非常重要的。

 ====> ====> ====> ====> ====>



