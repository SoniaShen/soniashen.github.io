Java 8 forEach examples:
web link: https://mkyong.com/java8/java-8-foreach-examples/

i.e. In Java 8, you can loop a Map with forEach + lambda expression


 -----> -----> -----> -----> ----->

web link: https://howtodoinjava.com/java8/foreach-method-example/
i.e. Create custom BiConsumer
we can create a custom biconsumer action taking key-value pairs from map and proces each entry one at a time.

 -----> -----> -----> -----> ----->

How to for each the hashmap? [duplicate]
web link: https://stackoverflow.com/questions/4234985/how-to-for-each-the-hashmap

i.e. 
HashMap<String, HashMap> selects = new HashMap<String, HashMap>();

for(Map.Entry<String, HashMap> entry : selects.entrySet()) {
    String key = entry.getKey();
    HashMap value = entry.getValue();

    // do what you have to do here
    // In your case, another loop.
}



 -----> -----> -----> -----> ----->
Sorting a HashMap according to keys in Java:
web link: https://www.geeksforgeeks.org/sorting-hashmap-according-key-value-java/

i.e. 2 Using TreeMap (Constructor):
        // TreeMap to store values of HashMap 
        TreeMap<String, Integer> sorted = new TreeMap<>(map); 
  
        // Display the TreeMap which is naturally sorted 
        for (Map.Entry<String, Integer> entry : sorted.entrySet())  
            System.out.println("Key = " + entry.getKey() +  
                         ", Value = " + entry.getValue());  



