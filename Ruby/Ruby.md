# Ruby Beginner

## General Note

### Command Line

- **echo** - to make a file with context.

- **cat** - to show file context.

```bash
$ echo "Hello my love" > test.txt
$ cat test.txt
```

### ri tool

- **ri** is a tool that allow you to display information about Ruby class, modules and methods.

```bash
# Find information about how file class seek method usage
$ ri "File#seek"
```

### Print out method

- **puts** will add new line in the end of string.
- **print** will not.

### String formatter

- #{} use for inster the variable inside the string.
- ${} use for applying same format for multiple value.

```ruby
formatter = "%{first} %{second} %{third} %{fourth}"

puts formatter % {first: 1, second: 2, third: 3, fourth: 4}
puts formatter % {first: "one", second: "two", third: "three", fourth: "four"}
puts formatter % {first: true, second: false, third: true, fourth: false}
puts formatter % {first: formatter, second: formatter, third: formatter, fourth: formatter}

puts formatter % {
  first: "I had this thing.",
  second: "That you could type up right.",
  third: "But it didn't sing.",
  fourth: "So I said goodnight."
}
```

```ruby
name = "YiChi"
puts "My name is #{name}"
```

### ARGV

- ARGV is argument variable. It holds the variables that you pass it from ruby script when you run it.
- Note 1: **gets.chomp** has problem when working with **ARGV**. Therefore, use **$stdin.gets.chomp** instead.
- Note 2: **gets** is the object that can get user input value with new line. **chomp** is a method that will remove the new line, just preserve the orginial input.

```ruby
eins, zwei, drei = ARGV
puts "First variable is #{eins}"
puts "Second variable is #{zwei}"
puts "Third variable is #{drei}"

puts "what is your least fav color?"
least_fav_color = $stdin.gets.chomp

puts "ok, i get it, you don't like #{least_fav_color} ?"
```

```bash
ruby ex2.rb one two three
```

### Using Alternative Syntax for Strings

- In order to handle special character.

```ruby
%{Sammy says, "I'm a happy shark!"}
# output will be Sammy says, "I'm a happy shark!"

droplets = 5
print %{Sammy says, "I just created #{droplets} droplets!"}
# output will be Sammy says, "I just created 5 droplets!"
```

Another way to achieve this

- **%q{}** = The syntax works exactly like single-quoted strings.
- **%Q{}** = The syntax works exactly like double-quoted strings.

### for - loop

```ruby
countries = ["Germany","Taiwan","Hungry"]
# 1. Most common one
countries.each do |item|
    puts item
end

# 2.
countries.each {|item| puts item}

# 3.
(0..5).each do |i|
  puts i
end
```

### Range Operator

- **..**: This operator is inclusive.
- **...**: This operator is exclusive the last one.

```ruby
# Print 0,1,2,3
(0..3).each do |i|
    puts i
end

# Print 0,1,2
(0...3).each do |i|
    puts i
end
```

## yield, PROCS, Lambdas

[Reference Souce](https://medium.com/podiihq/ruby-blocks-procs-and-lambdas-bb6233f68843)

### yield

- It's like callback, delegate. It give the block of code({}) to another method. **yield** keyword will execute the block you passed and continue executing the rest of code in the method.

```ruby
# Example 1
def calculation(a,b)
    yield(a,b)
end

# Give the block of code into calculation method
puts calculation(1,3) { |a,b| a + b }

# Exapmle 2
def funA
    yield
end

funA { puts "sometimes shortcuts do get you there faster"  }

# Example 3 pass parameter to your method like each method
[1,3,5].each { |num| puts num }

def my_method
    yield 7
    yield 17
end

my_method {|number| puts "Number is #{number}"}
```

- Is given a block?

```ruby
def funcA
    yield if block_given?
end
```

### PROCS

- A block of code that you can store in a variable
- To save you if you want to pass two blocks into a method.
- Proc objects are blocks of code that have been bound to a set of local variables. Once bound, the code may be called in different contexts and can still access those variables.

#### Defining procs

- You can use **Proc.new** or **proc** to create a proc.
- **&** keyword is used to let Ruby knows this is not a vairble but a proc.
- There are different ways of calling procs in our methods. Using call, () or using [].

```ruby
factor = Proc.new {|n| print n*2 }
# Or
factor = proc {|n| print n*2}
# Using the proc value
[3,2,1].each(&factor)
# > 642


def my_map(enumerable, &block)
  result = []
  enumerable.each { |element| result << block.call(element) }
  result
end
my_map(["foo", "bar"], &:upcase)
```

### Lambdas

- Can be defined using the method lambda or can be defined as stabby lambda

```ruby
lamb = lambda {|n| puts 'I am a lambda' }
lamb = -> (n) { puts 'I am a stuby lambda' }
```

### Difference between Proc and Lambdas

- Procs don't care about the correct number of arguments while lambdas does, lambdas will raise error if the arguments number are not correct.

- Procs return from home (the method where it is created), lambdas return from self.

```ruby
def my_proc_method
    x = Proc.new {return}
    x.call
    p "Text inside the method"
end
# Console result will be nil because of return
# Return inside Proc will skip the following code

def my_lambda_method
    x = lambda {return}
    x.call
    p "Text inside the method"
end
# Will print the text
```

Note: **&:methodName**

[Reference Source](https://www.brianstorti.com/understanding-ruby-idiom-map-with-symbol/)

````ruby
# Example 1
["emma","adole"].map(&:upcase)

# Example 2
(1..10).to_a.select do |x|
    x.even?
end

# Equals to
(1..10).to_a.select {|x| x.even?}

# Equals to (This is advance Ruby)
(1..10).to_a.select(&:even?)

```

### Symbo

[Reference Source](https://www.culttt.com/2015/04/22/what-are-symbols-in-ruby/)
````

### Symbo

- **$** this means global. Z.B: $stdin.
- **@** this means this object. Z.B: @name. It's like object property. Without **@** will be just in function scope variable.

### Shortcut

1. **%w(text)**: It is a shortcut for array which will convert text to array.

```ruby
#It will return an array with ["What","a","beautiful","day!"]
%w(What a beautiful day!)
```
