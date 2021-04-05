### Matchers

```ruby
it 'checks that a method changes object state' do
  numbers = [1, 2, 3]
  expect { numbers.push(4) }.to change { numbers.length }.from(3).to(4)
end
```

```ruby
it 'checks for the substring at the beginning' do
  expect('category').to start_with('cat')
end

it 'checks for the substring at the end' do
  expect('dopamine').to end_with('mine')
end
```



```ruby
it 'checks for object attributes and values' do
  expect(car).to have_attributes(maker: 'Volvo', model: 'XC40')
end
```