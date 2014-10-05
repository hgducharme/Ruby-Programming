#Classes

<br>

### General Syntax:

Ruby is an object-oriented-programming language (OOP), which means it manipulates programming constructs called objects. All objects have methods and attributes. For example: `Matz.length #==> 4`. In this case, the `“Matz”` object is a string, with a method of `.length`, and an attribute of `4`. What makes `Matz` a string though? The fact that it is an instance of the class `String`. A class is just a way of organizing and producing objects with similar methods and attributes.

Class syntax looks like this:

```ruby
class ClassName
 # Do something
end
```

<br>
<br>

### Class Names:

Class names start with an uppercase letter and use camelCase instead of snake_case. In this example, we tell ruby that we can’t to create a new class, then we put the `ClassName` to give the class a name, and then we insert whatever code inside that class. `ClassName` is now a class, just like `“Hello!”`, is a `String` (which is a class) and `4` is a `Fixnum` (which is also a class).

<br>

### Initialize Method & Creating a Class:

When creating a class, you want to create a method called `initialize`. When you create a new instance, it will run the `initialize` method, and execute any code in that method. `initialize`. takes however many arguments you tell it to take. In ruby, we use the `@` operator before a variable to signify that it is an instance variable. This means that the variable is attached to the instance of the class. They are unique to whatever instance is

For example:

```ruby
class Car
 def initialize(make, model)
  @make = make
  @model = model
 end
 end

time_machine = Car.new(DMC-12, DeLorean)
# ==> This is the DeLorean from Back to The Future
```

In this example, we created an instance `time_machine` of the class `Car. time_machine` has its own make of `DeLorean` and its own model of `DMC-12`. So these variables only belong to this instance, thus, this makes these variables instance variables.

<br>

### Creating a New Instance of a Class:

Creating a new instance of a class looks like this: `me = Person.new(“Eric”)`. Where `me` is a new instance of the class Person, and it takes an argument of `“Eric”`.

<br>

### Different Kinds of Variables:

Another important aspect of Ruby classes is scope. The scope of a variable is the context in which it’s visible to the program. Not all variables are accessible to all parts of the program. When dealing with classes, you can have variables that accessible to all parts of the program (global variables), variables that are only available to certain methods (local variables), and variables that are only available to a particular instance of a class (instance variables). The same goes for methods, some are available everywhere, some can only be accessible to members of that class, and some are only accessible to a particular instance.

<br>

### Naming Your Variables:

Instance variables start with the `@`operator. Class variables are like instance variables, but instead of belonging to an instance of a class, they belong to the class itself. Class variables always start with the `@@` operator. Global variables can be declared in two ways: The first is just to define the variable outside of any classes or methods, then it is global. If you want to make a variable global from inside a method or class, you start it with the `$`operator.

An example of a class with different kinds of variables:

```ruby
class Person
  @@people_count = 0
  def initialize(name, age, profession)
    @name = name
    @age = age
    @profession = profession
    @@people_count += 1
  end

  def number_of_instances
    return @@people_count
  end
end

batman = Person.new(“Bruce Wayne”, 35, “Superhero”)
superman = Person.new(“Clark Kent”, 35, “Superhero”)
bill_gates = Person.new(“Bill Gates”, 45, “Software Engineer”)

puts Person.number_of_instances
# ==> It would print 3, because we have batman, superman, and bill_gates
```

In this example, we create a class variable called `@@people_count` and set it to 0. Then we add it to the `initialize` method, and every time an instance is initialized, it adds one to `people_count`. We define a new method called `number_of_instances` and have it return the current `@@people_count`. We then print the `number_of_instances` method to the console to see how many instances have been created of the `People` class.

<br>

### Class Methods:

Just like how there are class variables, and instance variables, the same is true for methods. A class method belongs to the class as a whole, while an instance method belongs to certain instances.

Here is the comparison between the two:

```ruby
class Person
  @@people = []
  # This is a class variable that is equal to an empty array

  def initialize(name, age, profession)
    @name = name
    @age = age
    @profession = profession
    @@people << name
    # We are pushing the names of the people into the array
  end

  def Person.people_names
    # This is a class method. Syntax: ClassName.method_name
    puts @@people
  end

  # This is an instance method, that only applies to whatever instance we call it on
  def greeting
    puts “Hello, my name is #{name}, I’m #{age} years old and I work as a #{profession}!”
  end
end

eric = Person.new(“Eric”, 25, “Doctor”)

# Calling them would look like this:

Person.people_names
# We’re printing all the names of every instance of the class People

Person.greeting
# This would not work because Person doesn’t exist, it’s just a class

eric.greeting
# This would work, because Eric is an actual instance of the class Person
```

<br>
<br>

### Real-World Classes:

However, in the real world, most classes will not look like the examples above. They will more closely resemble real-world objects.

Here is an example of a class that would most likely be seen in commercial software:

```ruby
def create_record(attributes, raise_error = false)
  record = build_record(attributes)
  yield(record) if block_given?
  saved = record.save
  set_new_record(record)
  raise RecordInvalid.new(record) if !saved && raise_error
  record
end
```

Notice how it creates an instance of the  `RecordInvalid` class. The syntax should all be familiar, except the `raise` bit. All it does is generate a new `RecordInvalid` error if the user tries to create or save an invalid record.

<br>

### Inheritance:

Inheritance is the process by which one class takes on the methods and attributes of another, and it’s used to express an is-a relationship. For example, a human is-a mammal, so it could inherit it’s methods and attributes from the mammal class, but a human is not a fox, so it could not inherit its methods and attributes from the fox, despite them both being mammals. The class inheriting from another class is called the `sub-class` or the  `derived-class`. The class it is inheriting from is called the `super-class`, the  `parent`, or the `base class`.

Inheritance syntax works like so:

```ruby
class SubClass < BaseClass
  # Do something
end
```

Where `InheritingClass` is the new class that is being made, and the `BaseClass` is the class from which it is inheriting its methods and attributes from. You can read `<` as "inheriting from".

<br>

### Overriding Inheritance:

Sometimes you will want one class that inherits from another to not only take on the parent’s methods and attributes, but to also override one or more of them. For example: You might have an `Email` class that inherits from the `Message` class. Both classes will have a `send` method, but sending an email might require different protocols that `Message` doesn’t have. Instead of just creating a new method in your `Email` class specifically for that, you can just create a method named `send` and it will override the `send` method that it inherited from  `Message`.  Also, sometimes you will be working inside a `sub-class` and realize you have overwritten a method or attribute from its `super-class` that you actually need. No problem! You can directly access a `super-class`’s methods or attributes by using Ruby’s built in `super` keyword. When you call the `super` keyword form inside a `sub-class` method or attribute, it will tell Ruby to look in the `super-class` and find a method or attribute with the same name as the one from which `super` is called. Ruby will then use the `super-class` method/attribute instead.

<br>

### Multiple Inheritances:

Any given Ruby class can only have one parent class. Some languages allow a class to have more than one parent, which is called a multiple inheritance. This can get really ugly really fast, which is why Ruby doesn’t allow it. However, there are circumstances where you want to incorporate data or behavior from several classes into one sub-class. Ruby allows this through the use of mix-ins.

For example:

```ruby
class Creature
  def initialize(powers)
    @powers = powers
  end
end

class Human
  def initialize(name)
    @name = name
  end
end

class Dragon < Creature; end
# This is shorthand for creating a class
class Dragon < Human; end
# This is shorthand for creating a class

# ==> Outputs error: "superclass mismatch for class Dragon”
```

We tried to have `Dragon` inherit from both `Human` and `Creature`, but Ruby gave us an error that basically says “`Dragon` seems to be inheriting from more than one class, please fix this so that `Dragon` only has one `super-class`.”

<br>

### Public and Private Methods:

Ruby allows you to explicitly make some methods `public`, and some methods  `private`. `public` methods allow for an interface with the rest of the program. They say: “Hey! Ask me if you need to know something about my class or its instances!”. `private` methods on the other hand are for your classes to do their own work undisturbed. They don’t want anyone asking them anything, so they make themselves unreachable. Methods in Ruby are public by default. If you want to make it clear whether your method is public or private, then you have to put either `public` or `private` before your method definition.

Like so:

```ruby
class ClassName
  # Class stuff

  public
  def public_method
    # Code here
  end

  private
  def private_method
    # Code here
  end
end
```

Note that everything after the `public` keyword until the `end` of the class definition will then be public, unless we state otherwise. Private methods are private to the object that they are defined in. This means you can only call the method from inside other methods within that object. Another way to say it is that the method cannot be called using an explicit receiver. Receivers are the objects that methods are called on. For example: `object.method`, where `object` is the receiver of the `method`. In order to access private information, we have to create public methods that know how to get it. This separates the private implementation from the public interface.

<br>
<br>

### Example of Putting it All Together:

```ruby
class Account
  attr_reader :balance
  attr_reader :name
  def initialize(name, balance=100)
    @name = name
    @balance = balance
  end

  private

  def pin
    @pin = 1234
  end

  def pin_error
    return "Access denied: incorrect PIN."
  end

  public

  def display_balance(pin_number)
    if pin_number == pin
      puts "Balance: #{@balance}"
    else
      puts pin_error
    end
  end

  def withdraw(pin_number, amount)
    if pin_number == @pin
      @blanace -= amount
      puts "Withdrew #{amount}. New balance: #{balance}"
    else
      puts pin_error
    end
  end
end


checking_account = Account.new(“John Doe", 100_000_000)
checking_account.display_balance(1234)
```


