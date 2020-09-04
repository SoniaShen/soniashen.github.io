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


 -----> -----> -----> -----> ----->
Empty check with String[] array [duplicate]
web link: https://stackoverflow.com/questions/22162231/empty-check-with-string-array

i.e.
[1] Normally you would want to do something like:
--
if (arr != null && arr.length > 0) { ... }
for non-empty array.

[2] However, as you may suspect, someone have made utils for such kind of common action. For example, in Commons-lang, you can do something like:
--
if (ArrayUtils.isEmpty(arr)) {... }

[3] if you do a static import for ArrayUtils.isEmpty, this line can be even shorter and looks nicer:
--
if (isEmpty(arr)) { ... }


 -----> -----> -----> -----> ----->
Java Array of Strings:
web link: https://www.tutorialkart.com/java/java-array/java-string-array/

i.e. 
    String names[] = new String[10];
    String names[] = {"apple", "banana", "cherry", "orange", "mango"};










