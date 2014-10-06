# Hashes

<br>
<br>

### General Syntax:

Hashes are similar to JavaScript objects or Python dictionaries. Hashes are a collection of key-value pairs. Keys are the names of the values. Values are assigned to keys using the `=>` operator, called a hash-rocket.

<br>

### Creating a Hash:

You can create an empty hash using constructor notation like so: `my_hash = Hash.new`. Then you would add to the hash using bracket notation, like so: `my_hash["key1"] = value1`. If you are adding a string as a value, then you would use quotations, if not, you can leave the value as-is.

Or you can use hash literal notation which looks like this:

```ruby
hash_one = {
    "key1" => value1,
    "key2" => value2,
    "key3" => value3
}
```

<br>

### Accessing a Hash:

You can access objects inside of a hash just like an array: `hash_one["key1"]`. All keys need to strings inside brackets, and inside the hash. When using quotes around a key, you are looking for that specific key, inside a hash. When not using quotes, you are looking for a variable, inside that  hash.

<br>

### Iterating over a Hash:

Iterating over hashes needs two placeholder variables to represent each key-value pair. You would use syntax like so:

```ruby
hash_one.each do | key, value |
    puts "#{key} has the value of #{value}"
end
```

<br>

### Using Symbols as Keys:

Since Ruby 1.9.0 was released, common consensus in the Ruby community is to use symbols as keys, instead of strings. Ruby symbols are sort of like a name. Symbols are not strings. There can be multiple strings that all have the same value, but there can only be one copy of any particular symbol at any given time. Symbols are good for hash keys for a few reasons. Symbols can not be changed once they’ve been created. Only one copy of any symbol exists at any given time, so they save a lot of memory. Symbols as keys are faster than strings as keys, because of the past two reasons.

For example:

```ruby
movies = {
    top_gun: "Good",
    finding_nemo: "Awesome",
    lion_king: "Great"
}
```

Even though the colon `:` is at the end of the key, it is still accessed the same. Meaning, if you were to call the key, you would do it like this: `movies[:top_gun]` or `movies[:lion_king]`. So you won’t be needing the hash-rocket anymore :( . If you are familiar with JavaScript objects or Python dictionaries, then this should look familiar.
