# Python vs Ruby vs JavaScript

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

## Strings

### Slice

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

### Reverse

**In Python**

```python
s[::-1] # From the start to the end in steps of 1, counting backwards => "kjihgfedcba"
```

**In Ruby**

```ruby
s.reverse #=> "kjihgfedcba"
```

**In JavaScript**, there's no built-in function for this.

### Immutability

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

### Capitalization

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

### String Interpolation

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

**In JavaScript ES6**

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

**In JavaScript ES6**

```js
myList.pop();
myList.pop(1); //=> "b" Removes and returns the element at index 1
```

### Counting the items

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

### Sorting the items

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

### Reversing the items

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

## Tuples

**In Python**

Tuples, unlike lists, are _immutable_, to ensure elements don't get flipped or reassigned.

```python
my_tuple = ('a', 'a', 'b')
my_tuple.index('a')
my_tuple.count('a')
```

**In Ruby and JavaScript**, there's no concept of tuples.

## Named tuples

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
