# Ruby Data Structures
## Arrays

### Iterating over multi-dimensional arrays

A Multi-dimensional array looks like the following:

```Ruby
my_array = [["a","b"],["c","d"],["e","f"]]

```
To iterate over this you can nest the ```array.each``` method as so:

```Ruby
my_array.each { |x| x.each { |y| puts y}}
```
the above outputs:

    a
    b
    c
    d
    e
    f
