# OSOM
Original Structured Object Model, pronounce ['ɔsəm] same as awesome

OSOM full w3c DOM compatible, and with some extensions.

# Syntax
## Symbols
OSOM only use 8 symbols
```
, : ; {} ' " `
```
## String
OSOM provide 3 kinds of string: word, words, quoted string, or 5 kinds(3 quoted string). And quoted string allow multi lines.
```
string
multi words string
'quoted string with 
crossed
lines'
"It's a question.
NOTE there is no any escape char"
`line 1
line 2
lin 3'
```
### Structure
dead simple plain old c structure style
```
name: value;
array values: value1, value2, value3, allow null element, , , other element
nest names: nest key1: nest key2: nest key not allow null element: value or value array;
name1: name2: key1, key2, key3: value or value array;
nest object{
  key: value2;
}
empty element {}
non array key allows multiple nest element {
/*element1 with key value pair*/ 
key: value;
}{
/*element can be empty, NOTE empty not null*/
}{}{
key: value;
}
```
# Sample
```javascript
// normal attributes
 name: value
 name: v1, v2
 name: , v2, ,,, vn
 name: ;
 // value element
 name;
 // multiple value elements
 n1, n2, n3;
 // normal elements
 name {...}
 name {...}{...}
 // empty elements
 name {}
 name {}
 // nested names
 n1: n2: n3: value(s)
 n1: n2: n3 {...}({...})
 n1: n2: n3 {} ({})
 // multiple names
 n1, n2, n3: value(s)
 n1, n2, n3 {...} // only one element
 n1, n2, n3 {} // only one empty element
 // multiple names must be the last part of nest names
 key1: key2: key3: n1, n2, n3: value(s)
 key1: key2: key3: n1, n2, n3: {...}
 key1: key2: key3: n1, n2, n3: {}

```
