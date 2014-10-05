# Procs

<br>

### Summary:
A proc is a saved block we can use over and over again.

<br>

### General Syntax:

Since blocks are not objects, and cannot be stored in variables along with all the other powers that objects have, we have procs to fill in this role. Procs are sort of like a “saved block”. Just like you can give a bit of code a name and turn it into a method, you can give blocks a name and turn it into a proc. With a block, you have to write your code out every time you use it. However, with procs, you can store this block code, write it only once, and then use it multiple times!

<br>

### Creating a Proc:

To create a proc, all you have to do is call `Proc.new`, and then pass in the block of code that you want to store. Any time you pass a proc to a method that usually expects a block, you have to use the ampersand (`&`) operator to then call that proc’s instructions (or block of code). Whenever calling a proc in a method that usually takes a block, make sure to put the proc inside parenthesis like so: `.some_method( &some_proc )`. Or a simpler version is to use the `.call` method. It would look like this: `some_proc.call`.

For example:

```ruby
multiples_of_3 = Proc.new do |n|
    n % 3 == 0
end

(1..100).to_a.select(&multiples_of_3)

# ==> 3, 6, 9, 12, 15, 18, 21, 24, 27 ...
```

Another example:

```ruby
numbers = [5, 10, 15, 20, 25, 30]

cubed = Proc.new { |n| puts n ** 3 }
numbers.map( &cubed )

# ==> Cubes each element in the number array, and then puts them on the console
```

<br>
<br>

### Blocks vs. Procs:

The benefits of using procs is that since procs are full-fledged objects, they have all the powers and abilities that objects do. Also, unlike blocks, procs can be called over and over again without rewriting them. This saves time and prevents you from having to write the block multiple times.

You can also convert symbols into procs using the ampersand (`&`) operator.

For example:

```ruby
strings = ["1", "2", "3"]
nums = strings.map(&:to_i)

# ==> [1, 2 ,3]
```

Another example:

```ruby
numbers_array = [1, 2, 3, 4, 5]
    strings_array = numbers_array.map(&:to_s)

# ==> ["1", "2", "3", "4", "5"]
```

<br>
<br>
<br>
<br>

# Lambdas

<br>

### Summary:
A lambda is just like a proc, only it cares about the number of arguments it gets and it returns to its calling method rather than returning immediately.

<br>

### General Syntax:

Like procs, lambdas are objects too. With the exception of a little syntax and a few behavioral quirks, lambdas are identical to procs. Lambdas are defined like this: `lambda { |param| block }`. Lambdas are useful in the same situation that you would use procs.

For example:

```ruby
strings = ["leonardo", "donatello", "raphel", "michaelangelo"]

symbolize = lambda { |name| name.to_sym } nil
strings.collect(&symbolize)

# ==> [:leonardo, :donatello, :raphel, :michaelangelo]
```

<br>
<br>

### Lambdas vs. Procs:

There are not many differences between lambdas and procs. However, there are a few: First, lambdas checks the number of arguments passed to it, while procs do not. This means that lambdas will throw in an error if you pass in the wrong number of arguments, and a proc will just ignore any unexpected arguments and assign `nil` to any that are missing. Second, when a lambda returns a value, it sends the control back to the calling method. When procs return a value, they do it immediately without going back to the calling method.

An example between procs & lambdas:

```ruby
def batman_ironman_proc
    victor = Proc.new { return "Batman will win!" }
    victor.call
    "Iron Man will win!"
end

puts batman_ironman_proc

def batman_ironman_lambda
    victor = lambda { return "Batman will win!" }
    victor.call
    "Iron Man will win!"
end

puts batman_ironman_lambda

# ==> Batman will win!
# ==> Ironman will win!
```

See how the proc prints out `"Batman will win!"`? That shows that the proc instantly returns the value and doesn’t shift the control back to the method. The lambda however returns the value then gives the control back to the method. Since methods return the last expression if no return is defined, `"Ironman will win!"` gets printed to the console.

<br>

### Passing Lambdas to Methods:

Just like procs also, we need to use the ampersand (`&`) operator at the beginning of the lambda name when we pass it to a method. This will convert the lambda into a block for the method to run.

Another example:

```ruby
my_array = ["raindrops", :kettles, "whiskers", :mittens, :packages]

symbol_filter = lambda { |x| x.is_a? Symbol }
symbols = my_array.select(&symbol_filter)
```

     # ==> [:kettles, :mittens, :packages]
