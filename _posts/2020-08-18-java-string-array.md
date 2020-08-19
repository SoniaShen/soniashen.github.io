How to trim white space from all elements in array?
web link: https://stackoverflow.com/questions/9864568/how-to-trim-white-space-from-all-elements-in-array

i.e.
String[] array2 = Arrays.stream(array).map(String::trim).toArray(String[]::new);

 -----> -----> -----> -----> -----> 
sort array of string in alphabetical order:
web link: https://howtodoinjava.com/java-examples/sort-string-array-alphabetically/

i.e. Using Java 8 Stream API
strArray = Stream.of(strArray).sorted().toArray(String[]::new);

 -----> -----> -----> -----> ----->
How to convert Array to Stream:
web link: https://mkyong.com/java8/java-how-to-convert-array-to-stream/

i.e. Object Arrays
For object arrays, both Arrays.stream and Stream.of returns the same output.

 -----> -----> -----> -----> ----->
Comparing Arrays in Java Examples:
web link: https://www.codejava.net/java-core/collections/comparing-arrays-in-java-examples

i.e. compares two arrays of Strings:
boolean equal = Arrays.equals(headings1, headings2);







