# ljson

Light JSON is a minified JSON format without parentheses or delimiters such as { } etc.



## Example

```
# it is comments
# simple data type
null null
bool true
int 0
float 0.0
string myvalue
string_space "my value"
text 
"
multiline text example
text multiline example
example text multiline
"
# mixed objects
object
    key_1 value1
    key_2 value2
    subobject
        key_3 value3
        key_4 value4
array_of_bool
    true
    false
    true
array_of_int
    0
    1
    2
array_of_flaot
    0.0
    1e14
    3.14
array_of_string_line
    value 1
    value 2
    value 3
array_of_mixed
    true
    null
    value
    0
    0.1
# linear array notation
array_of_bool_line true false true
array_of_int_line 0 1 2
array_of_float_lien 0.1 -2.3 1e12
array_of_string "value 1" "value 2" "etc"
```



# Rules

1. Each line can contain # character for comment.
0. The format contains key and value pairs.
0. Each line has the key or delimiter in the begining.
0. The key and value are separated by spaces.



# Reserved words

1. null - empty value
0. true - boolean true value
0. false - boolean false value

