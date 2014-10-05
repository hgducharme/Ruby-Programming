# Basic Syntax

<br>
<br>

### Declaring Variable Names

In ruby, when declaring variable names always use *snake_case*, not *camelCase*. Each time you need to name something that requires multiple words, separate those words using underscores `_`, and make the whole title lowercase. Names should never start or contain uppercase letters.

<br>

### Comments

In ruby a single line comment looks like this:

```ruby
# this is a single line comment
```

A multiple line comment looks like this:

```ruby
=begin
This is a multiple line comment
This is line number two
This is line number three
=end
```

<br>

### Symbols

Symbols are primarily used as hash keys, or to reference method names. Once a symbol is created, it can not be changed, and only one copy of a symbol can exist at any given time. There can not be multiple symbols with the same value. Symbols look like this: `:symbol`. They have a colon, and then are followed by a name.

<br>

### Prints, Puts, Return, & Yield
---
<br>

#### Prints:

The print command takes whatever instructions you give it, and puts it on the screen, on the same line.

```ruby
print "Hello world!"
print "Hello world!"
```

Output:

```ruby
"Hello world!Hello world!"
```
<br>

### Puts:

The puts command creates a new line for each thing that you have it print.

```ruby
puts "Hello world!"
puts "Hello world!"
```

Output:

```ruby
"Hello world!"
"Hello world!"
```
<br>

### Return:

The return command just returns the value of something. If you don’t tell ruby what to return, it will always return the last expression in the method code block.

```ruby
def double(n)
  return n * 2
end

output = double(6)
output += 2
puts output
# puts ==> 14
```

In the example above, we defined a method called `double`. Inside the method, we `return n * 2`. We then set a variable `output` which is equal to `double(6)`. with the argument of `6`. We then add two to `output`, and we puts the variable `output`. If you don’t tell ruby what to return, it will always return the result of the last expression in the method code block.

<br>

### Yield:

The yield command allows for methods (that don’t have the capability already) to accept a block of code. Methods that accept blocks have a way of transferring control from the method to the block and back to the method again. You can build this into methods by using the yield command.

```ruby
def block_test
    puts "We're in the method!"
    puts "Yielding to the block…"
    yield
    puts "We're back in the method!"
end

block_test { puts "--- We're in the block!" }
```

Output:

```ruby
"We’re in the method!"
"Yielding to the block…"
"--- We’re in the block!"
"We’re back in the method!"
```

You can also pass parameters to the yield command.

```ruby
def yield_name(name)
    puts "In the method! Let's yield."
    yield("Kim")
    puts "In between the yields!"
    yield(name)
    puts "Block complete! Back in the method."
end

yield_name("Eric") { |n| puts "My name is #{n}." }
```

Output:

```ruby
"In the method! Let’s yield!"
"My name is Kim."
"In between the yields!"
"My name is Eric."
"Block complete! Back in the method!"
```

The `yield_name method` is defined with one parameter, `name`. On line 8, we call the `yield_name` method and supply the argument `"Eric"` for the `name` parameter. Since `yield_name` has a `yield` statement, we will also need to supply a block. Inside the method, on line 2, we first `puts` an introductory statement.
Then we `yield` to the block and pass in `"Kim"`.
In the block, `n` is now equal to `"Kim"` and we `puts` out `"My name is Kim."` Back in the method, we `puts` out that we are in between the yields. Then we `yield` to the block again. This time, we pass in `"Eric"` which we stored in the `name` parameter. In the block, `n` is now equal to `"Eric"` and we `puts` out `"My name is Eric."` Finally, we `puts out a closing statement.
