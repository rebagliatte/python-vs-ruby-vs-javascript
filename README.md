# Ruby vs Python

## Division

In Python we use true division.

```python
1/2 #=> 0.5
```

In Ruby we use integer division.

```ruby
1/2 #=> 0
```

## Strings

### Slice

In Python, we use the `[]` function, passing in three params:
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

In Ruby, we use the `slice` function, passing two params:
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

### Reverse

In Python

```python
s[::-1] # From the start to the end in steps of 1, counting backwards => "kjihgfedcba"
```

In Ruby

```ruby
s.reverse #=> "kjihgfedcba"
```

### Immutability

In Python Strings are **not** mutable! (meaning you can't use indexing to change individual elements of a string)

```python
s = "Sun"
s[0] = "F"
# Boom!
```

In Ruby Strings are mutable.

```ruby
s = "Sun"
s[0] = "F"
s #=> Fun
```

### Capitalization

In Python

```python
s.upper()
s.lower()
```

In Ruby

```ruby
s.upcase
s.downcase
```
