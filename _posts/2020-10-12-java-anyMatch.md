web link: https://www.logicbig.com/how-to/java/lambda-list-contains-a-substring.html
i.e.
List<String> list = Arrays.asList("Apple", "Orange", "Banana");
    String string = "A box of Oranges";
    boolean match = list.stream().anyMatch(s -> string.contains(s)));
    System.out.println(match);
---
List<String> list = Arrays.asList("Apple", "Orange", "Banana");
   String string = "A box of Oranges";
   boolean match = list.stream().anyMatch(string::contains);
   System.out.println(match);




web link: https://www.baeldung.com/foreach-java#:~:text=Since%20the%20introduction%20of%20Lambda%20expressions%20in%20Java,good%20practices%20of%20working%20the%20new%20language%20feature.

Guide to the Java 8 forEach
i.e.
BiConsumer ? 
(key, value) -> System.out.println(key + " " + value)

[strongly suggested!!!]












