# Arrays

<br>
<br>

### General Syntax:

If you want to save a range of numbers, or pack multiple values into one variable, then you use the data structure called an array.  An array is a list of items between square brackets. Data inside an array does not have to be in any order, and arrays can hold any type of data, whether it be a string, an integer, booleans, objects, even additional arrays.

Array syntax looks like this:

```ruby
example_array = ["String", 5, "Birds", 231, "baseball"]
```

<br>

### Accessing Items in an Array:

You can access items inside an array like so: `example_array[0]`. Arrays start counting at number 0. So the element in the first position is at index 0, then the seconds is at index 1, and the third is at index 2, etc.

<br>

### Adding to An Array:

Adding to an array can be done in two ways: The first looks like this: `example_array.push("string")` or `example_array << "string"`.

<br>

### Iterating over Arrays:

Iterating over arrays uses syntax that looks like this: `example_array { |i| puts i }`

Iterating over multi-dimensional arrays is a little bit different:

```ruby
# s stands for sandwiches
s = [["ham", "swiss"], ["turkey", "cheddar"], ["roast beef", "gruyere"]]

# if we just wanted to access "swiss", we would do this:
s[0][1]
# We access "s", then we access the array in the 0th position,
# then the element in the 1nth position


# if we wanted to print out every element, we would do this:
s.each do |sub_array|
    sub_array.each do |x|
        puts x
    end
end
# first we iterate over each object inside ’s’
# then we iterate over each object inside ‘sub_array'
```
