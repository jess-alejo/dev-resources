## Accessing Arrays

We can access an array element by targeting its index. Array index starts at 0.

```ruby
%w[apple banana cherry][0] # => "apple"
%w[apple banana cherry][1] # => "banana"
```

<br>

We may use a range to crop or slice an array.

```ruby
# get the item from index 1 to 2 using inclusive range
%w[apple banana cherry][1..2] # => ["banana", "cherry"]

# get the item from index 1 to 2 using exclusive range
%w[apple banana cherry][1...2] # => ["banana"]
```

<br>

We can use negative index to access array starting from the last item

```ruby
%w[apple banana cherry][-1] # => ["cherry"]
%w[apple banana cherry][-2] # => ["banana"]
```

<br>

We can use a combination of positive and negative indexes if we are more interested in the rest of the items

```ruby
%w[I V X L C D M][4..-1] # => ["C", "D", "M"]
```

<br>

Besides range, we can use #first and #last methods to get the first or last item(s) in an array

```ruby
[1, 2, 3, 4, 5].first     # => 1
[1, 2, 3, 4, 5].first(2)  # => [1, 2]

[1, 2, 3, 4, 5].last      # => 5
[1, 2, 3, 4, 5].last(2)   # => [4, 5]
```
