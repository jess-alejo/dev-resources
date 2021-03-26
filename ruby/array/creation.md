## Create arrays in different ways

Create array with Array::new

```ruby
Array.new(3, 'x')
#=> ["x", "x", "x"]
```

<br>

Create array of strings with percent string literal

```ruby
%w[apple banana cherry]
#=> ["apple", "banana", "cherry"]

# use \ to escape space in multiple words
%w[Big\ Bang\ Theory Darwin's\ Evolution]
#=> ["Big Bang Theory", "Darwin's Evolution"]

# use %W to apply interpolation
name = 'World'
#=> "World"
%W[Hello\ #{name} Goodbye\ #{name}]
#=> ["Hello World", "Goodbye World"]
```

<br>

Create array of symbols with percent string literal

```ruby
%i[index show new create edit update destroy]
#=> [:index, :show, :new, :create, :edit, :update, :destroy]
```
