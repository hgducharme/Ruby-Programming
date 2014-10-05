# Documentation - WIP

<br>
<br>

**Table of Contents**
---
1. Iterators
2. String Methods
3. Array Methods
4. Hash Methods
5. Class Methods

<br>
<br>
<br>
<br>

### Iterators
---
<br>
When we loop over an array or hash, we say that we iterate over it. Iterators are methods that go through each instance of whatever object we apply it to.

.each: The each iterator applies an expression to each element of an object.  The variable inside the || is just a placeholder name for each element in the object.

     The syntax looks like this:

     object.each { |item| #Do something }
—or—
     object.each do |item|
          #Do something
     end

.collect - This method is used to iterate over each element inside an array. Similar to .each.

.map - This method is used to iterate over each element inside an array. Similar to .collect.

.next - Century Gothic

.upto - This is a much more "Ruby” version of doing a for loop. Example:
     95.upto(100) {|num| puts num}. This will print all the numbers between 95, and 100. It will also include the numbers 95 and 100. This also works for the alphabet.

.downto - This is a much more "Ruby” version of doing a for loop. It is exactly the same as the .upto method, except for descending order. Example: 100.downto(50) {|num| puts num}. This will print all the numbers between 50 and 100 in decending order. It will also include the numbers 50 and 100. This will also work for the alphabet.

.inject - Century Gothic

.reduce - Century Gothic

<br>
<br>
<br>

### String Methods
---
<br>
.length - The length method will return the number of characters (includes spaces and symbols) that are present in the string

.reverse - The reverse method will reverse the letters in the string, so that “String” would then become “gnirtS"

.upcase - The up-case method will turn a string to ALL UPPER CASE letters

.downcase - The down-case method will turn a string into all lower case letters

.capitalize - The capitalize method will capitalize the first letter of the string

.reversecase - The reverse-case method will swap the cases of every letter in the string, so that “StRiNg” will become “sTrInG"

.sub - The substitution method will substitute the first instance of whatever it is you are looking for, to whatever it is you tell it to put.

     The syntax looks like this:

     “String”.sub(“B”, “R”) = “Btring”


.gsub - The global substitution method will substitute every instance of whatever you are looking for.

     The syntax looks like this:

     “strings”.gsub(“s”, “Z”) = “ZtringZ”


.split - The split method takes in a string, and then returns it as an array. It will divide the text wherever it sees that bit of text, called a delimiter. The example below tells ruby to split the string whenever it sees a space.

     The syntax looks like this:

     text.split(“ ”)

.to_sym: - This method is used to convert a string, into a symbol. “string”.to_sym  # ==>  :string

.to_s: - This method is used to convert other types of objects, into a string. 5.to_s  # ==>  “5”

.slice: - Century Gothic

<br>
<br>
<br>

### Array Methods
---
<br>
.index - Century Gothic

.sort - The sort method, when called on an array, will sort the elements by ascending order. If the array has numbers, it will sort it starting with 1, and put them in order. If the array contains elements, it will sort it alphabetically. In order to reverse this by sorting from descending order. You can either call .reverse on the .sort method, or you can use the<=>operator.

     For example:

     my_array = [1, 2, 3, 4, 5]

     my_array.sort!  —or—  my_array.sort!.reverse!
—or—
     my_array.sort! { |firstNum, secondNum| secondNum <=> firstNum }


.sort_by - Century Gothic

.push - This method adds elements to the end of an array. FIrst you call the .push method on the array you want to add to, then it takes an argument as to what you want to push.

     For example:

     my_array = [1, 2, 3, 4, 5]
     numbers = []

     my_array.each do |x|
          numbers.push(x)
     end

.select - Century Gothic

<br>
<br>
<br>

### Hash Methods
---
<br>
.each_key - Century Gothic

.each_value - Century Gothic

.select - Century Gothic

<br>
<br>
<br>

### Class Methods
---
<br>
attr_reader - Century Gothic

attr_writer - Century Gothic

attr_accessor - Century Gothic
