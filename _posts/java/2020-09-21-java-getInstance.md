java中getInstance() 的理解:
web link: https://blog.csdn.net/TTTZZZTTTZZZ/article/details/87883519

P.S. Create getter() function -> instead of using global static parameter
     Actually, don not use static unless it's global uniq parameter, which will never changed! [suggested] 

i.e.
    public static ImmJNICertHandler getInstance() {
        return instance;
    }



