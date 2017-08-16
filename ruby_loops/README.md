# Ruby Loops

 <br>


### Table of Contents
1. `for` loops
2. `while` loops
3. `until` loops
4. `loop` loops
5. `.times` iterator loop

<br>
<br>
<br>

## A 'for' loop:
```ruby
for i in 1..50
    puts "#{i}"
end
```

1. For every number between 1 - 50
2. Using the inclusive `..` operator tells the computer to include the last number in the loop
3. Will `puts` numbers 1 - 50
4. Using the exclusive `...` operator tells the computer to exclude the last number from the loop
5. Will `puts` the numbers 1-49
6. Display the number on the console
7. Ends instructions for the loop

<br>

## A 'while' loop:
```ruby
i = 1
while i <= 50
    puts "#{i}"
    i += 1
end
```

1. Sets variable `i` equal to one
2. While `i` is less than or equal to 50, do the block of code (will print numbers 1 -50)
3. Display the number on the console
4. Increment `i` by one every time, that way the loop will end at some point
5. Ends instructions for the loop

<br>

## An 'until' loop:
```ruby
i = 1
until i > 50
    puts "#{i}"
    i += 1
end
```

1. Sets variable `i` equal to one
2. Until `i` is greater than 50, run the block of code (will print numbers 1-50)
3. Display `i` on the console
4. Increment `i` by one every time, that way the loop will end at some point
5. End the instructions for the loop

<br>

## A 'loop' loop:
```ruby
i = 1
loop do
    puts "#{i}"
    i += 1
    break if i > 50
end
```

1. Sets variable `i` equal to one
2. Create a `loop`, and run the block of code
3. Display `i` on the console
4. Increment `i` by one every time, that way the loop will end at some point
5. Break the loop if `i` becomes greater than 50
6. End the instructions for the loop

<br>

## A '.times' iterator loop:
```ruby
5.times do
    puts "Hello world!"
end
```

1. Run this loop five times, and do the block of code
2. Display the string on the console
3. End the instructions for this loop
