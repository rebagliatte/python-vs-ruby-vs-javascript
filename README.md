# Python vs Ruby vs JavaScript

## Integers

**In Python**, we use true division.

```python
1 / 2 #=> 0.5
```

**In Ruby**, we use integer division.

```ruby
1 / 2 #=> 0
```

**In JavaScript**, we use true division.

```javascript
1 / 2; //=> 0.5
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

**In Ruby**, Strings are mutable.

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

**In JavaScript ES6**

```javascript
let myList = ["a", "b", "c"];
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
