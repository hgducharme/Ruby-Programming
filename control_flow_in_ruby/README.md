# Control Flow in Ruby

<br>
<br>

## `if` Statements:

`if` statements takes an expression, and runs it to see if it is true or false. If the expression is `true`, then it runs the block of code. If the expression is `false`, then it moves onto the next piece of instructions.

An example:

```ruby
if 4 < 5
    puts "Four is less than five."
end
```

If an `if` statement is short, and only requires one line, then you can use a simpler syntax. The statement has a syntax like this: `expression if boolean`. It would be said like so: Do this expression if the boolean is true or false (which ever one you put). The order they go in, is extremely important! If they’re not in that order, it won’t work.

Using the example above, it would look like this:

```ruby
puts "Four is less than five" if 4 < 5
```

<br>

## `if/else` Statements:

The partner to the `if` statement, is the `else` statement. An `if/else` statement says to ruby: “if this expression is true, run this code block; otherwise, run the code block after the `else`.

For example:

```ruby
if 4 > 5
    puts "This should not run because four is not greater than five."

# Realize there is no end statement after this if statement

else
    puts "The if statement is false, so the else code is being ran."
end
```

The more concise version of the `if/else` statement is called the ternary conditional expression. It is called ternary because it takes three arguments: a boolean, an expression to evaluate if the statement is true, and an expression for if the statement is false. It has syntax which looks like this: `boolean ? Do this if true: Do this if false`. It would be said like so: Evaluate this boolean, if it’s true do the first expression, if it’s false do the second expression. The order they go in is extremely important! If they’re not in that order, it won’t work.

For example:

```ruby
puts 4 < 5 ? "Four is less than five" : "Four is not less than five"
```

<br>

## `elsif` Statements

If you need more than just two options, then you can implement an elsif statement.

For example:

```ruby
if x < y  # Assumes x and y are defined
    puts "x is less than y!"
elsif x > y
    puts "x is greater than y!"
else
    puts "x equals y!"
end
```

<br>

## `unless` Statements

Sometimes you want to use control flow to see if a statement is false, rather than if it’s true. This is where you use the unless statement. Lets say that you don’t want to eat unless you’re hungry, and when you’re not hungry then you want to draw pictures.

You would write something like this:

```ruby
hungry = false

unless hungry
    puts "Let’s go draw a picture!"
else
    puts "Let’s go get some food."
end
```

If an `unless` statement is short, and only requires one line, then you can use a simpler syntax. The statement has a syntax like this: `expression unless boolean`. It would be said like so: Do this expression unless the boolean is true or false (which ever one you put). The order they go in is extremely important! If they’re not in that order, it won’t work.

Using the example above, it would look like this:

```ruby
hungry = false
puts "lets go draw a picture" unless hungry
```

<br>
<br>

## `switch` Statements

When you have multiple options, you can use the `switch` statement. It allows you to put multiple `when` statements, or conditions, and then which ever one is true, it will run that condition. It is exactly like an `elsif` statement, but better for situations where there are multiple choices, because we don’t want to use too many `elsif` statements.

The syntax looks like this:

```ruby
puts "What is your favorite color?"
color = gets.chomp

switch color
    when ‘blue’
        puts "Blue"
    when ‘red’
        puts "Red"
    when ‘green’
        puts "Green"
    when ‘purple’
        puts "Purple"
    when ‘yellow’
        puts "Yellow"
    else
        puts "You did not put a color"
end
```

However, there is a simpler way to do it, if the conditions don’t have a big block of code. Meaning, if they only have one line of instructions, then you can fold it up into a simpler syntax like so:

```ruby
puts "What is your favorite color?"
color = gets.chomp

case color
    when ‘blue’ then puts “Blue”
    when ‘red’ then puts “Red”
    when ‘green’ then puts “Green”
    when ‘purple’ then puts “Purple”
    when ‘yellow’ then puts “Yellow”
    else puts “You did not put a color”
end
```
