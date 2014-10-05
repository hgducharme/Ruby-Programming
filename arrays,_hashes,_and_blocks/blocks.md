# Blocks

<br>
<br>

### General Syntax:

Blocks are a set of code that explains what to do. It is nothing more than a set of instructions. Blocks are on of the only things in Ruby that is not an object. Since blocks are not objects, they can not be stored to variables and don’t have all the powers that other objects have. Blocks are similar to anonymous functions in JavaScript and lambdas in Python. Blocks can be defined with either the key words: `do` and `end`, or with curly braces `{ }`.

For example:

```ruby
1.times do
    puts "I’m a code block!"
end
```

or

```ruby
1.times { puts "I’m a code block too!" }
```

<br>
<br>

### Passing Blocks to Methods:

Passing a block to a method is a great way of abstracting certain tasks from the method and defining those tasks whenwe call a method. Abstraction is an important idea in computer science, and you can think of it as meaning "making something simpler.”

For example:

```ruby
# The block, {|i| puts i}, is passed the current array item
# each time it is evaluated. This block prints the item
[1, 2, 3, 4, 5].each { |i| puts i }

# This block prints the number 5 for each item.
# It chooses to ignore the passed item, which is allowed
[1, 2, 3, 4, 5].each { |i| puts 5 }
```

Whenever the `each` method is called, it is passed a block as a parameter, with a set of instructions as to what needs to be done.
