# Ruby Collections

### Array Methods

1. Chunk

- It is an Enumerable method that groups together **consecutive elements** for which the block returns the same thing. In this case, the block just returns the character itself so chunk will form groups of identical characters.

```ruby
my_arr = ["A","A","B","B","B"]
result = my_arr.chunk {|x| x}

#result will be an enumerable array like this [["A", ["B", "B"],["B", ["B", "B", "B"]]]
```
