#domain/programming

# indexing (Python)

Indexing is how you access individual characters (or elements) in a string by their position number.

- Each character has a position called an **index**; indexing is zero-based, so the first character is at index `0`, the second at index `1`, and so on.
- Syntax: `string[index]`
- Negative indices count from the end: `-1` is the last character, `-2` the second-to-last.
- Use `len()` to get a string's length — the count of characters, not a position.

python

```python
my_str = "Hello world"

len(my_str)     # 11
my_str[0]       # H
my_str[6]       # w
my_str[-1]      # d
my_str[-2]      # l
```

Strings are **immutable** — you can reassign the variable to a new string, but you can't modify a string in place via indexing.

python

```python
greeting = 'hi'
greeting = 'hello'          # OK — reassignment
print(greeting)             # hello

greeting[0] = 'H'           # TypeError: 'str' object does not support item assignment
```