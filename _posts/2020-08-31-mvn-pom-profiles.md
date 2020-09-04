Invalid Content Was Found Starting With Element 'country'. 
web link: https://stackoverflow.com/questions/17173383/invalid-content-was-found-starting-with-element-country-one-of-country-is

i.e.
As written, your schema expects the "global" countries, name and city elements to be in the http://localhost:8080/ajaxprac namespace, but the "local" elements (those declared inside a complexType, i.e. country and cities) to be in no namespace. You probably want to add elementFormDefault="qualified"

 -----> -----> -----> -----> -----> -----> 






















