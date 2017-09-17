# Ruby Methods

<br>

Since everything in Ruby is an object, everything in Ruby has built in abilities called methods. You can think of methods as "skills" that these objects can perform.

<br>

### Calling methods on an object:

Calling a method uses syntax like this: `object.method` where you first type the object you want to use, then use the `.` operator, and lastly the method you want to use

<br>

### Defining methods:

It starts with the keyword `def`, which is short for define. Methods have three parts:

1. The Header - Includes the `def` keyword, the name of the method, and any arguments the method takes
2. The Body - This is the code block that will be run. It describes the procedures the method carries out
3. End - The method is then closed with the keyword `end`



An example would look like this:

```ruby
def method_name
    puts “This is a new method!”
end
```

<br>

### Calling a method:

To call a method all you have to do is type in the name of the method. Nothing else. So for the example above, if we wanted to call that method, we would do this: `method_name` on a new line inside the file. All that is needed to call the method is to just type in the name of it on a new line, and then it will call the method and proceed with the instructions for that method.

<br>

### Parameters & arguments:

If a method takes arguments, we say that it accepts  or expects those arguments. The argument is the actual piece of code you put between the method's parenthesis when you call it. The parameter is the name that you put between the parenthesis when you define it.

An example would look like this:

```ruby
def square(n)
    puts n ** 2
end

square(10)
# ==> prints “100”
```


In the example above, we gave the method square a parameter of n, and when we called the method, we gave it an argument of 10.

<br>

### Splat Arguments:

On regular methods, you never really know exactly what argument you’re going to get, so you use the parameter as a temporary placeholder. However, what if you don’t know how many arguments you’re going to get? Then you use the splat argument: `*`. You place your splat argument then follow it with the parameter you give it. It signals to ruby: “Hey Ruby, I don’t know how many arguments there are about to be, but it could be more than one."

For example:

```ruby
def what_up(greeting, *bros)
    bros.each { |bro| puts "#{greeting}, #{bro}!" }
end

what_up("What up", "Justin", "Ben", "Kevin Sorbo")
```

Output:

```ruby
"What up, Justin!"
"What up, Ben!"
"What up, Kevin Sorbo!"
```
