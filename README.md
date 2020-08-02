# Table of Contents

- [Data Types](#data-types)
  - [Strings](#strings)
    - [Mutating strings](#mutating-strings)
    - [Interpolating strings](#interpolating-strings)
    - [Slicing strings](#slicing-strings)
    - [Reversing strings](#reversing-strings)
    - [Capitalizing strings](#capitalizing-strings)
  - [Integers](#integers)
  - [Booleans](#booleans)
  - [None (Python), nil (Ruby), null (JavaScript)](#none-python-nil-ruby-null-javascript)
- [Truthyness](#truthyness)
- [Operators](#operators)
  - [Equality](#equality)
  - [Boolean](#boolean)
  - [Relational](#relational)
- [Data Structures](#data-structures)
  - [Lists (Python) / Arrays (Ruby and JavaScript)](#lists-python--arrays-ruby-and-javascript)
    - [Creating a list](#creating-a-list)
    - [Adding an item](#adding-an-item)
    - [Removing items](#removing-items)
    - [Counting items](#counting-items)
    - [Getting the minimum and maximum items](#getting-the-minimum-and-maximum-items)
    - [Checking for the inclusion of an item](#checking-for-the-inclusion-of-an-item)
    - [Sorting items](#sorting-items)
    - [Reversing items](#reversing-items)
    - [Zipping lists/arrays together](#zipping-listsarrays-together)
    - [Comprehending Lists](#comprehending-lists)
  - [Ranges](#ranges)
  - [Sets](#sets)
  - [Tuples](#tuples)
    - [Named tuples](#named-tuples)
  - [Dictionaries (Python) / Hashes (Ruby) / objects (JavaScript)](#dictionaries-python--hashes-ruby--objects-javascript)
    - [Checking for the inclusion of a key](#checking-for-the-inclusion-of-a-key)
  - [Statements](#statements)
    - [If](#if)
    - [Ternary if](#ternary-if)
    - [Switch](#switch)
    - [For](#for)
      - [Iterating over lists/arrays](#iterating-over-listsarrays)
      - [Iterating _with an index_ over lists/arrays](#iterating-with-an-index-over-listsarrays)
      - [Iterating over dictionaries/hashes/objects](#iterating-over-dictionarieshashesobjects)
    - [While](#while)
    - [Break](#break)
    - [Continue/Next](#continuenext)
- [Arguments](#arguments)
  - [Passing positional arguments](#passing-positional-arguments)
  - [Passing named/keyword arguments](#passing-namedkeyword-arguments)

# Data Types

## Strings

### Mutating strings

**In Python**, Strings are _immutable_.

```python
s = "Sun"
s[0] = "F" # => TypeError: 'str' object does not support item assignment
```

**In Ruby**, Strings are _mutable_.

```ruby
s = "Sun"
s[0] = "F"
s #=> Fun
```

**In JavaScript**, Strings are _immutable_.

```javascript
let s2 = "Sun";
s2[0] = "F"; // The action is not performed but no error is triggered
console.log(s2[0]); // Sun
```

### Interpolating strings

**In Python**

```python
q = "quick"
f"The {q} brown box"
```

**In Ruby**

```ruby
q = "quick"
"The #{q} brown box"
```

**In JavaScript**

```js
q = "quick";
`The #{q} brown box`;
```

### Slicing strings

**In Python**, we use the `[]` function, passing in three params:

1. Start index
2. End index (which is _excluded_)
3. Stepper

```python
s = "abcdefghijk"
s[0:3]  # From index 0 to 3 (exclusive) => "abc"
s[:3]   # From the start to index 3 (exclusive) => "abc"
s[1:]   # From index 1 to the end => "bcdefghijk"
s[::2]  # From the start to the end in steps of 2 => "acegik"
```

**In Ruby**, we use the `slice` function, passing two params:

1. Start index
2. Number of chars you want to take

```ruby
s = "abcdefghijk"
s.slice(0,3)  # From 0, take the 3 first chars => "abc"
```

Alternatively, you can pass a range (considering the end index is _included_)

```ruby
s = "abcdefghijk"
s[0..3] # From index 0 to 3 (inclusive) => "abcd"
```

Or a regex, with an optional capture group

```ruby
s = "abcdefghijk"
s[/[aeiou]/]      #=> "a"
```

**In JavaScript**, we use the `slice` function, passing two params:

1. Start index
2. End index (which is _excluded_)

```ruby
s = "abcdefghijk"
s.slice(0,3) # From index 0 to 3 (exclusive) => "abc"
```

### Reversing strings

**In Python**

```python
s[::-1] # From the start to the end in steps of 1, counting backwards => "kjihgfedcba"
```

**In Ruby**

```ruby
s.reverse #=> "kjihgfedcba"
```

**In JavaScript**

There's no built-in method to do this.

### Capitalizing strings

**In Python**

```python
s.upper()
s.lower()
```

**In Ruby**

```ruby
s.upcase
s.downcase
```

**In JavaScript**

```javascript
s.toUpperCase();
s.toLowerCase();
```

## Integers

**In Python**

```python
1 / 2 #=> 0.5 True Division
```

**In Ruby**

```ruby
1 / 2 #=> 0 Integer Division
1.0 / 2.0 #=> 0.5 Float Division
```

**In JavaScript**

```javascript
1 / 2; //=> 0.5 True Division
```

## Booleans

**In Python**

```python
True
False
```

**In Ruby**

```ruby
true
false
```

**In JavaScript**

```javascript
true;
false;
```

## None (Python), nil (Ruby), null (JavaScript)

**In Python**

```python
None
```

**In Ruby**

```ruby
nil
```

**In JavaScript**

```javascript
null;
```

# Truthyness

For quick reference:

|                     | Python | Ruby | JavaScript |
| ------------------- | ------ | ---- | ---------- |
| `None`/`nil`/`null` | ❌      | ❌    | ❌          |
| `""`                | ❌      | ✅    | ❌          |
| `[]`                | ❌      | ✅    | ✅          |

**In Python**

```python
not(not(None)) #=> False
not(not("")) #=> False
not(not([])) #=> False
```

**In Ruby**

```ruby
!!nil #=> False
!!"" #=> True
!![] #=> True
```

**In JavaScript**

```javascript
!!null; //=> False
!!""; //=> False
!![]; //=> True
```

# Operators

## Equality

**In Python and Ruby** we use _strict_ equality.

```python
==
```

**In JavaScript** we have two distinct operators for _abstract_ and _strict_ equality. [See MDN for more details](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#A_model_for_understanding_equality_comparisons).

```javascript
== // Abstract equality comparison (compares values after converting them to the same type)
=== // Strict equality comparison
```

## Boolean

**In Python** we use:

```python
and
or
not
```

_Note the `&&`, `||` and `!` boolean operators are [**not** available in Python](https://docs.python.org/3/reference/expressions.html#boolean-operations)._

**In Ruby** we use:

```ruby
&&
||
!
```

_Note that though the `and`, `or` and `not` operators are available in Ruby, they are better suited as control flow operators. If we choose to use them as boolean operators (which is against general advice), we must be aware of the fact that they have a lower precedence than their counterparts (`&&`, `||` and `!`)._

**In Javascript** we use:

```javascript
&&
||
!
```

_Note the `and`, `or` and `not` operators are **not** available in JavaScript._

## Relational

These work in the same way in all three languages.

```python
>
<
>=
<=
```

# Data Structures

## Lists (Python) / Arrays (Ruby and JavaScript)

### Creating a list

**In Python**

```python
my_list = ['a', 'b', 'c']
```

**In Ruby**

```ruby
my_list = ['a', 'b', 'c']
```

**In JavaScript**

```javascript
const myList = ["a", "b", "c"];
```

### Adding an item

**In Python**

```python
my_list.append('d')
```

**In Ruby**

```ruby
my_list.push('d')
```

**In JavaScript**

```js
myList.push("d");
```

### Removing items

**In Python**

```python
my_list.pop()
my_list.pop(1) #=> "b" Removes and returns the element at index 1
```

**In Ruby**

```ruby
my_list.pop()
my_list.pop(2) #=> ["b", "c"] Removes and returns as many items as indicated, in this case 2 items
```

**In JavaScript**

```js
myList.pop();
myList.pop(1); //=> "b" Removes and returns the element at index 1
```

### Counting items

**In Python**

```python
len(my_list)
```

**In Ruby**

```ruby
my_list.length
```

**In JavaScript**

```js
myList.length();
```

### Getting the minimum and maximum items

**In Python**

```python
min([1, 2, 3])
max([1, 2, 3])
```

**In Ruby**

```ruby
[1, 2, 3].min
[1, 2, 3].max
```

**In JavaScript**

```js
Math.min(...[1, 2, 3]);
Math.max(...[1, 2, 3]);
```

### Checking for the inclusion of an item

**In Python**

```python
1 in [1, 2, 3]
```

**In Ruby**

```ruby
[1, 2, 3].include?(1)
```

**In JavaScript**

```js
[1, 2, 3].includes(1);
```

### Sorting items

**In Python**

```python
my_list.sort() # Sorts the list in place, doesn't return anything
```

**In Ruby**

```ruby
my_list.sort # Sorts
my_list.sort! # Sorts the list in place
```

**In JavaScript**

```js
myList.sort(); // Sorts the list in place, and returns it
```

### Reversing items

**In Python**

```python
my_list.reverse() # Reverses the list in place, doesn't return anything
```

**In Ruby**

```ruby
my_list.reverse # Reverses
my_list.reverse! # Reverses the list in place
```

**In JavaScript**

```js
myList.reverse(); // Reverses the list in place, and returns it
```

### Zipping lists/arrays together

**In Python**

```python
a = [1, 2, 3]
b = ["a", "b", "c"]

for item in list(zip(a, b)):
    print(item)

# (1, 'a')
# (2, 'b')
# (3, 'c')
```

**In Ruby**

```ruby
a = [1, 2, 3]
b = %w[a b c]

a.zip(b).each do |item|
  puts item
end

# 1
# a
# 2
# b
# 3
# c
```

**In JavaScript**

There's no built-in method to do this.

### Comprehending Lists

**In Python**

```python
new_list = [some_method(i) for i in old_list if condition_method(i)]
```

**In Ruby and JavaScript**, there's no built-in method to do this.

## Ranges

**In Python**

```python
range(10) # From 0 to 10 (exclusive) => [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
range(0, 10) # From 0 to 10 (exclusive)
range(0, 10, 2) # From 0 to 10, in steps of 2 => [0, 2, 4, 6, 8]
```

To convert ranges to lists, we do `list(range(0,10))`.

**In Ruby**

```ruby
0..10 # From 0 to 10 (inclusive) => [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
0...10 # From 0 to 10 (exclusive) => [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

To convert ranges to arrays, we do `(0..10).to_a`.

**In JavaScript**

There's no built-in method to create ranges.

## Sets

**In Python**

Sets are unordered collections of unique values.

```python
my_set = set()
my_set.add(1) # {1}
my_set.add(2) # {1,2}
my_set.add(2) # {1,2}
```

**In Ruby**

In order to use them, the Set module needs to be required.

```ruby
require 'set'
my_set = Set[]
my_set.add(1)
my_set.add(2)
my_set.add(2)
```

**In JavaScript**

```javascript
mySet = new Set();
mySet.add(1);
mySet.add(2);
mySet.add(2);
```

## Tuples

**In Python**

Tuples, unlike lists, are _immutable_, to ensure elements don't get flipped or reassigned.

```python
my_tuple = ('a', 'a', 'b')
my_tuple.index('a')
my_tuple.count('a')
```

**In Ruby and JavaScript**, there's no concept of tuples.

### Named tuples

**In Python**

```python
color = (red=255, green=0, blue=0)
```

**In Ruby**, there's no concept of named tuples, however, `Struct` or `OpenStruct` could be used as alternatives.

```ruby
require 'ostruct'

Color = Struct.new(:red, :green, :blue)
color = Color.new(255, 0, 0)
```

**In JavaScript**, there's no concept of named tuples, object literals are used instead.

```javascript
const color = { red: 255, green: 0, blue: 0 };
```

## Dictionaries (Python) / Hashes (Ruby) / objects (JavaScript)

**In Python**

```python
my_dict = {
  'apple': 2.99,
  'oranges': 1.99,
  'watermelon': 0.5
}
my_dict['apple']
my_dict.get('banana', 2.5) # Augments the method above, providing a default value
my_dict.keys()
my_dict.values()
my_dict.items() # Converts the dictionary into a list
```

**In Ruby**

```ruby
my_hash = {
  apple: 2.99,
  oranges: 1.99,
  watermelon: 0.5
}
my_hash[:apple]
my_hash.fetch(:banana, 2.5) # Augments the method above, providing a default value
my_hash.keys
my_hash.values
my_hash.to_a # Converts the hash into an array
```

**In JavaScript**

```js
myObj = {
  apples: 2.99,
  oranges: 1.99,
  watermelon: 0.5,
};
myObj.apple;
Object.keys(myObj);
Object.values(myObj);
Object.entries(myObj);
```

### Checking for the inclusion of a key

**In Python**

```python
"a" in {"a": 1}
```

**In Ruby**

```ruby
{ a: 1 }.key?(:a)
```

**In JavaScript**

```js
"a" in { a: 1 };
```

## Statements

### If

**In Python**

```python
if True:
    print("✅")
elif True:
    print("❌")
else:
    print("❌")

```

**In Ruby**

```ruby
if true
  puts('✅')
elsif true
  puts('❌')
else
  puts('❌')
end
```

**In JavaScript**

```javascript
if (true) {
  console.log("✅");
} else if (true) {
  console.log("❌");
} else {
  console.log("❌");
}
```

### Ternary if

**In Python**

```python
"✅" if True else "❌"
```

**In Ruby and JavaScript**

```ruby
true ? "✅" : "❌"
```

### Switch

**In Python**

Switch statements are not available.

**In Ruby**

```ruby
location = 'Beach'

case location
when 'Beach'
  puts 'Flip flops'
when 'Home'
  puts 'Chewbacca slippers'
when 'Mountain', 'Jungle'
  puts 'Boots'
else
  puts 'Sneakers'
end
```

**In JavaScript**

```javascript
const location = "Beach";

switch (location) {
  case "Beach":
    console.log("Flip flops");
    break;
  case "Home":
    console.log("Chewbacca slippers");
    break;
  case "Mountain":
  case "Jungle":
    console.log("Boots");
    break;
  default:
    console.log("Sneakers");
}
```

### For

#### Iterating over lists/arrays

**In Python**

```python
for n in [1, 2, 3]:
    print(n)
```

**In Ruby**

```ruby
%w[a b c].each do |n|
  puts n
end
```

**In JavaScript**

```JavaScript
for (n of [1, 2, 3]) {
  console.log(n);
}
```

#### Iterating _with an index_ over lists/arrays

**In Python**

```python
for index, n in enumerate([1, 2, 3]):
    print(f"index: {index}, n: {n}")
```

**In Ruby**

```ruby
[1, 2, 3].each_with_index do |n, index|
  puts "index: #{index}, n: #{n}"
end
```

**In JavaScript**

```JavaScript
for ([index, n] of [1, 2, 3].entries()) {
  console.log(`index: ${index}, n: ${n}`);
}
```

#### Iterating over dictionaries/hashes/objects

**In Python**

```python
my_dict = {"a": 1, "b": 2, "c": 3}

for k, v in my_dict.items():
    print(f"k:{k}, v:{v}")
```

**In Ruby**

```ruby
my_hash = { a: 1, b: 2, c: 3 }

my_hash.each do |k, v|
  puts "k: #{k}, v: #{v}"
end
```

**In JavaScript**

```JavaScript
const myObject = { a: 1, b: 2, c: 3 };

for (const k in myObject) {
  console.log(`k:${k}, v:${myObject[k]}`);
}
```

### While

**In Python**

```python
x = 0

while x < 11:
    print(x)
    x += 1
else:
    print("Stop")
```

**In Ruby**

```ruby
x = 0

while x < 11
  puts x
  x += 1
end
```

**In JavaScript**

```JavaScript
let n = 0;

while (n < 11) {
  console.log(n);
  n++;
}
```

### Break

Breaks out of the closest enclosing loop. The same `break` keyword is used in all three languages.

### Continue/Next

Skips the rest of the current iteration and goes to the top of the closeset enclosing loop.

**In Python**

```python
continue
```

**In Ruby**

```ruby
next
```

**In JavaScript**

```JavaScript
continue;
```

# Arguments

## Passing positional arguments

**In Python**

```python
def my_function(a, b, c=3):
    return f"a:{a}, b:{b}, c:{c}"


print(my_function(1, 2))  # => a:1, b:2, c:3
```

**In Ruby**

```ruby
def my_function(a, b, c = 3)
  "a:#{a}, b:#{b}, c:#{c}"
end

puts(my_function(1, 2)) # => a:1, b:2, c:3
```

**In JavaScript**

```JavaScript
function myFunction(a, b, c = 3) {
  return `a:${a}, b:${b}, c:${c}`;
}

console.log(myFunction(1, 2)); //=> a:1, b:2, c:3
```

## Passing named/keyword arguments

**In Python**

```python
def my_function(a, b, c=3):
    return f"a:{a}, b:{b}, c:{c}"


print(my_function(b=2, a=1))  # => a:1, b:2, c:3
```

**In Ruby**

```ruby
def my_function(a:, b:, c: 3)
  "a:#{a}, b:#{b}, c:#{c}"
end

puts(my_function(b: 2, a: 1)) # => a:1, b:2, c:3
```

**In JavaScript**

```JavaScript
function myFunction({ a, b, c = 3 } = {}) {
  return `a:${a}, b:${b}, c:${c}`;
}

console.log(myFunction({ b: 2, a: 1 })); //=> a:1, b:2, c:3
```
