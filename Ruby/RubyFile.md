# Ruby File

## Action Parameters

- **r** - reading
- **a** - appending to a file
- **w** - writing
- **w+** - reading and writing
- **a+** - opening a file for reading and appending
- **r+** - opening a file for updating, both reading and writing

### Writing

```ruby
# Solution 1
File.open("mytext.text","w+"){ |f|
    f.write("Dogs, Cats, Lions, Tigers")
}

# Solution 2
file = File.new("mytext.text","w+")
file.puts("This is another text")
file.close
```

### Reading

```ruby
# Read line
my_text = File.read("mytext.text")
p my_text

# Read to array
p my_text.split(', ')
```

### Deleting

```ruby
File.delete("mytext.text")
```

### Appending

- This can use in writing log.

```ruby
10.times do
    sleep 1
    File.open("mytext.text","a") {|f|
        f.puts "Server starts at: #{Time.new}"
    }
```
