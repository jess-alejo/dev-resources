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

```ruby
describe 'include matcher' do
  describe('plethora') do
    it { is_expected.to include 'thor' }
  end

  describe([1, 3, 5]) do
    it { is_expected.to include 1 }
  end

  describe({ a: 1, b: 2, c: 3 }) do
    it { is_expected.to include(:a, :c) }
    it { is_expected.to include({ b: 2 }) }
  end
end
```

```ruby
describe 'raise_error matcher' do
  describe([1, 2, 3]) do
    it 'raise TypeError' do
      expect { subject + 1 }.to raise_error(TypeError)
    end

    it 'raise NoMethodError' do
      expect { subject.call }.to raise_error(NoMethodError)
    end
  end
end
```