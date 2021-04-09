### Special Constants

Get the filename of the current executing file

```ruby
# script.rb
puts "find me at #{File.realpath(__FILE__)}"
```

```sh
ruby script.rb
# find me at /Users/jess/github/dev-resources/script.rb
```

Get the directory from current executing file

```ruby
# script.rb
puts __dir__
```

```sh
ruby script.rb
# /Users/jess/github/dev-resources
```
