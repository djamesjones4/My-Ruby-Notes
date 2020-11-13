# Ruby Data Structures

## Hashes
<p><strong>Hashes are a collection of key-value pairs </strong></u> similar to Javascript objects.

Hash syntax looks like this:
</p>

```Ruby
# This is literal notation for creating a hash
my_hash = {
  key1 => value1,
  key2 => value2,
  key3 => value3
}
```

<p>
Javascript object notation:
</p>

```JS
myObj ={
  key1: value1,
  key2: value2,
  key3: value3
}

```

### Hash.new

```Ruby
# The following creates  a new hash that is the equivalent of open and closed curly braces - {}
Hash.new
# note that Hash is capitalized
```
We can add to a hash using literal notation or by using ```Hash.new``` and then using bracket notation to add to the hash like so:
```Ruby
my_hash = Hash.new

my_hash["thing1"] = "hat"
my_hash["thing2"] = "cat"
my_hash["thing3"] = "mischief"

puts my_hash
# output -->
# {
# "thing1"=> "hat",
# "thing2"=> "cat",
# "thing3"=> "mischief"
# }

```
### Iterating over a Hash
Similarly to an array we can use ```Hash.each``` to iterate over a Hash
For example:
```Ruby
family = { "Homer" => "dad",
  "Marge" => "mom",
  "Lisa" => "sister",
  "Maggie" => "sister",
  "Abe" => "grandpa",
  "Santa's Little Helper" => "dog"
}

family.each { |x, y| puts "#{x}: #{y}" }

```

The above would output:

    Homer: dad

    Marge: mom

    Lisa: sister

    Maggie: sister

    Abe: grandpa

    Santa's Little Helper: dog

Alternately ```array.each do``` can be used as such:

```Ruby
family.each do |key, value| puts "#{key}: #{value}"
end

# or

family.each do |key, value| puts
```
The above puts out:

    Homer: dad

    Marge: mom

    Lisa: sister

    Maggie: sister

    Abe: grandpa

    Santa's Little Helper: dog

### Sorting a Hash

#### ```hash.sort_by```
note: this method returns an array

Hashes can be sorted using the ```hash.sort_by``` method as such:

```Ruby
puts "Please type some words: "
text = gets.chomp
words = text.split(" ")
frequencies = Hash.new(0)
words.each do |word| frequencies[word] += 1
frequencies = frequencies.sort_by do |word, count|
  count
end
```
In the above example input is taken from the user and the input string is then split into an array. We then create an empty hash call frequencies. The array, words, is then iterated over, putting each index as a key for the frequencies hash simultaneously incrementing the value by 1. We then sort the frequencies hash according to the value of the key-value pair.
