web link: https://www.decodejava.com/java-io-bytearrayinputstream.htm

 =====> =====> =====> =====>
Do I need to close a ByteArrayInputStream?
web link: https://stackoverflow.com/questions/5118204/do-i-need-to-close-a-bytearrayinputstream
 -----> -----> -----> ----->
i.e. 
You don't have to close ByteArrayInputStream, the moment it is not referenced by any variable, garbage collector will release the stream and somebytes (of course assuming they aren't referenced somewhere else).

However it is always a good practice to close every stream, in fact, maybe the implementation creating the stream will change in the future and instead of raw bytes you'll be reading file? Also static code analyzing tools like PMD or FindBugs (see comments) will most likely complain.
-----> -----> -----> -----> ----->
If you are bored with closing the stream and being forced to handle impossible IOException, you might use IOUtils:
    IOUtils.closeQuietly(stream);
 =====> =====> =====> =====>



Java String to InputStream:
web link: https://www.baeldung.com/convert-string-to-input-stream

i.e. @Test
public void givenUsingPlainJava_whenConvertingStringToInputStream_thenCorrect() 
  throws IOException {
    String initialString = "text";
    InputStream targetStream = new ByteArrayInputStream(initialString.getBytes());
}
Note that the getBytes() method encodes this String using the platform’s default charset so to avoid undesirable behavior you can use getBytes(Charset charset) and control the encoding process.








