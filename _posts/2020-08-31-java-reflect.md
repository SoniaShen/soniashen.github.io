使用Mockito对类成员变量进行Mock:
web link: https://blog.csdn.net/fenglibing/article/details/16842655

i.e. 通过使用反射的方式:
  Field testAField = oneClass.getClass().getDeclaredField("testA");
	testAField.setAccessible(true);
	testAField.set(oneClass, testA);


 -----> -----> -----> -----> -----> -----> 







