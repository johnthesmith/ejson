# ljson

1. Light JSON is a minified JSON format with minimum numbers of lexemes.



## Example

```
# This is example of LJSON fromat
# Simple data types
null null
bool true
int 0
float 0.0
string myvalue
string_with_space my value
text
"
multiline text example
text multiline example
example text multiline
"
# Complex data types
object
    key_1 value1
    key_2 value2
    subobject
        key_3 value3
        key_4 value4
array_vertical
    true
    false
    null
    1
    3.14e1
    "value 1"
    object
        key value
array_linear true, 1, 3.14, value with space,
# Some cases
"key with space" value
```



# Transformations

0. The format offers:
    1. the uniquely invertible transformations ```ljson = f( json )```.
    0. the specific invertible transformations ```json = j( ljson )``` without coments.
0. LJSON can not be converted to text without a newline character.



# Rules

1. Each line can contain # character at the begining for the comment.
0. The format contains key and value pairs.
0. The key and value are separated by spaces.
0. Each line has the key or delimiter in the begining.
0. The format allows blank lines in the body.



# Value data types

Values ​​can be typed based on syntax:

1. [null](#null)
0. [bool](#bool)
0. [int](#int)
0. [flaot](#float)
0. [string](#string)
0. [array](#array)
0. [object](#object)



## null

1. The empty value, writen as ```null```
```
key1 null
key2 null
```



## bool

1. The bool value, written as ```true``` or ```false```
```
key1 true
key2 false
```



## int

1. The int value, written as ```0```, ```1```, ```-2``` etc

```
legs 4
age_year 2
```



## float

0. The float value, written as ```0.0```, ```-0.1```, ```1e12``` etc
```
constants
    pi 3.14159265
    e 2,7182818284
    h 6,582119514e-16
```



## string

1. The string value 
    1. contains any characters, except single [lexemes](№lexemes).
    0. may be wounded at ```"``` double quots
```
meeting
    guest Jhoan Smith
    master Bob
    password "true"
```



## array

1. The array value writen following methods:
    1. linear notation with the ```.``` (comma) delimiter:
    ```
    gerlfrends Jesica, Samanta, Lilu
    ```
    3. multiline values notation withot with the ```\n``` (new line) delimiter:
    ```
    girlfrends
        Jesica
        Samanta
        Lilu
    ```
    2. multiline pair notation with the ```\n``` (new line) delimiter:
    ```
    girlfrends
        first   Jesica
        second  Samanta
        current Lilu
    ```
    3. multiline subobjects notation with the ```.``` (point) delimiter:
    ```
    girelfrends
        .
            order first
            name Jesica
        .
            order second
            name Samanta
        .
            order current
            name Lilu
    ```



## object

1. The object value writen following method:
```
user
    login masquarade
    hash a9bf7f39-3960-4717-9a63-921b825cdb24
    first_name Jhoan
    last_name Smith
    office 402
```
2. For array of objects look at [array](#array)



# Lexemes

Format offers next lexemes:

1. `null` - empty value
0. `true` - boolean true value
0. `false` - boolean false value
0. ` ` space character:
    1. at the begining of the line new pair or array element is defined 
    0. the first space after the key separates the value 
    0. the following spaces in the value define the value like a string
    0. between `"` mean the space in the value
0. `\n`new line character:
    1. after value finished the pair
    0. after array value finished the value
    0. between `"` add new line in string or text value
0. `,` comma character 
    0. define the value as array at linear notation and separated elements of array
    0. between `"` mean the comma in the value
0. `"` double quotes
    1. defines for key name with a space
    0. defines a string value or for string value with a space



# example

Look at the following examples.



## empty file

```ljson
```

```json
{}
```



## null

```ljson
key null
```

```json
{
    "key":null
}
```



## Man

```ljson
first_name  jhoan
last_name   smith
age         32
```

```json
{
    "first_name": "jhoan",
    "last_name": "smith",
    "age": 32
}
```



## Integers

```ljson
0,1,2,3,4,5,6,7,8,9
```

```json
[
    0,1,2,3,4,5,6,7,8
]
```



## Object with propertyes and subobnjects

```ljson
object
    color red
    size huge
    parent
        id apple
```

```json
{
    "object":
    {
        "color":"red",
        "size":"huge"
        "parent":
        {
            "id":"apple"
        }
    }
}
```



## Array of sting for animals and bioms

```ljson
animals
    "green frog"
    "yellow lion"
    "gray spider"
bioms swamp, savannah, desert
```

```json
{
    "animals":
    [
        "green frog",
        "yellow lion",
        "gray spider"
    ],
    "bioms":
    [
        "swamp", "savannah", "desert"
    ]
}
```



## Array of objects

```ljson
array
    .
        color orange
        size huge
    .
        color red
        size medium
```

```json
{
    "array":
    [
        {
            "color":"orange",
            "size":"huge"
        },
        {
            "color":"red",
            "size":"medium"
        }
    ]
}
```



## Text

```ljson
top
"
this is a multiline 
text example
"

bottom
"
this is a multilne
bottom text
"
```

```json
{
    "top":"this is a multiline \ntext example"

    "bottom":"this is a multilne \nbottom text"
}
```
