# Python

## General Note

### Tuples

- It is a immutable list.

### Difference between **List** and **Numpy Array**

|                         | List                  | Numpy Array                   |
| ----------------------- | --------------------- | ----------------------------- |
| Data Type               | Multiple Type         | One Type                      |
| Slice to a new variable | Create another memory | Reference to the original one |

### DataFrame

1. Find a single value

- **.at**: For labels, even integers are treated as labels.
- **.iat**: For integer locations.

```ruby
    df.at(2,'BirthRate') # Get the row label name 2 and column name label Birthrate
    df.iat(1,2) # Get the row which at 1 index and column which at 2 index
```
