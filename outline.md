# What is a hash? 

+ Hashes, just like arrays, are a way for us to store lists of data in Ruby. Unlike an array though, a hash is not indexed by number. Instead, hashes are structured with keys and value. 

+ Each key/value pair makes up one unit in the hash. The entire collection of key/value pairs, which are comma separated, is enclosed in curly braces { }.

Let's take a look

my_hash = {"key1" => "value 1", "key2" => "value2"}

+ You can think of a hash as a dictionary. The key is the reference point that is set equal to an associated value. A vocabulary dictionary actually makes a pretty good example of the hash structure:

dictionary = {

  "apple" => "a delicious fruit", 
  "this readme" => "wonderful and informative piece of reading", 
  "Moby Dick" => "a novel by my good friend, Herman Melville"

}

+ You can think of the data stored in a hash as being associative. In other words, keys point to data that is related to that key. 

# Constructing Hashes

+ We can make a new hash via the class constructor or the literal constructor, just like arrays.

The Class Constructor

my_hash = Hash.new
  => {} 
The Literal Constructor

my_hash = {}
  => {}

+ Initializing a hash that already contains data is a lot like initializing an array with data. We use the literal constructor:

pets = {"cat" => "Maru", "dog" => "Pluto"}
  => {"cat" => "Maru", "dog" => "Pluto"}


# Example usages: named data, keeping count

FIRST EXAMPLE
Let's take a look at a few examples of the usefullness of using hashes to store associated data. 

Here we have a hash in which the keys are the name of the type of information we are storing in the values:

the_rock = {"name" => "Dwayne, The Rock, Johnson", "weight" => "a lot"}

If we tried to represent this same information as an array, it would look something like this:

the_rock = ["name", "Dwayne, The Rock, Johnson", "weight", "a lot"]

Then, in order to access The Rock's name, we would have to use the following line of code:

the_rock[1]

That requires us to remember, every time we want to access The Rock's name, that it is stored at the first index of the_rock array. That is too hard to keep track of.

Unlike arrays which store data in numbered indexes, hashes store data in unique keys—like fields for a contact in your address book.

SECOND EXAMPLE: herman melville

In this example, we've traveled back in time to the 1800s to work with our friend Herman Melville at the NY customs house. We are talling up a new shipment and we need to keep track of the quantity of each item we are storing. 

Let's say our shipment contains five (5) whale bone corsets, two (2) porcelain vases, and three (3) oil paintings. If we tried to store them in an array in list form, it would look like this:

old_fashioned_things = [
  "whale bone corset", 
  "whale bone corset", 
  "whale bone corset", 
  "whale bone corset", 
  "whale bone corset", 
  "porcelain vase", 
  "porcelain vase", 
  "oil painting", 
  "oil painting", 
  "oil painting"
]
As it stands, there is no way for us to include the count of each item in a way that associates the item to its count, so we have to store a separate occurrence of that item in order to track the shipment. Certainly for a small list this is manageable, but what happens when the shipment of Herman's first printing of Moby Dick arrives? We'd have to store 10,000 occurrences of the book instead of recording the count as value. That's no good!

So, how else can we help Herman keep track of how many of each item are included in the shipment? Here's where a hash can come in handy. With a hash, we can store a list of associated key/value pairs. In other words, we can store the pairs of item/count:

old_fashioned_things = {
  "whale bone corset" => 5, 
  "porcelain vase" => 2, 
  "oil painting" => 3
}

first_printing = {
  "Moby Dick" => 10000
}



# What is a hash key?

+ all data types
+ must be uniqe

Each key in a hash must be unique. The value associated with that key is then accessed by accessing the hash using the key, rather than an index number. Let's take a look:

the_rock = {"name" => "Dwayne Johnson", "name" => "The Rock", "weight" => "a lot"}
And then tried to access The Rock's name:


the_rock["name"]

# Retrieving Data from Hashes

Retrieving data from a hash is similar to retrieving data from an array, but instead of giving an array the index number in brackets [i] we give a hash the name of the key [key]. If an array is a list in which we access index items by their number, a hash is a dictionary in which we access values by their key.

pets = {"cat" => "Maru", "dog" => "Pluto"}

pets["cat"]
  => "Maru"
Using [] is referred to as the "bracket method".

#Adding Objects to Hashes

Adding items to hashes is easy. Instead of << (the shovel method) that we use to add items to arrays, hashes use an [:key]= method to add data. The full syntax for this takes the form of:

hash[:key]= value

Let's keep working on our shipping manifest by adding the 10 jars of molasses from our shipment:

shipping_manifest = {
  "whale bone corset" => 5, 
  "porcelain vase" => 2, 
  "oil painting" => 3
}

shipping_manifest["jar of molasses"] = 10

puts shipping_manifest
#  └── shipping_manifest = {
  "whale bone corset" => 5, 
  "porcelain vase" => 2, 
  "oil painting" => 3, 
  "jar of molasses" => 10
}