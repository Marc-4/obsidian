`char* str;` // variable that points to the address of size `char`
`char* str = malloc(10);` // allocates memory of size char x 10
`char buffer[10];` `char* str = buffer;` // same as above

`int address = &str;` // address now holds the address str is pointing to
### DEREFERENCING
*if str is a String*
`(*str).length();` // access the length function on the object
`(*str)[0];` // access the 0th index of the object
### REFERENCE
`String& str;` // variable that holds a reference or memory address of the object

`str.length();` // valid
