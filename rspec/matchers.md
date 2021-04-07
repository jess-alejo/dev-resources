### Matchers

```ruby
context 'using change matcher' do
  it 'checks that a method changes object state' do
    numbers = [1, 2, 3]
    expect { numbers.push(4) }.to change { numbers.length }.from(3).to(4)
  end
end
```

```ruby
context 'using start_with matcher' do
  it 'checks for the substring at the beginning' do
    expect('category').to start_with('cat')
  end
end

context 'using end_with matcher' do
  it 'checks for the substring at the end' do
    expect('dopamine').to end_with('mine')
  end
end
```

```ruby
context 'using have_attributes matcher' do
  describe({a: 1, b: 2, c: 3}) do
    it { is_expected.to have_attributes(keys: [:a, :b, :c]) }
    it { is_expected.to have_attributes(values: [1, 2, 3]) }
  end
end
```

```ruby
context 'using include matcher' do
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
context 'using raise_error matcher' do
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

```ruby
context 'using respond_to matcher' do
  describe('a simple string') do
    it { is_expected.to respond_to :size }
    it { is_expected.to respond_to :upcase }
  end

  describe([1, 2, 3]) do
    it { is_expected.to respond_to :size }
    it { is_expected.to respond_to(:push).with(1).arguments }
  end

  describe({a: 1, b: 2, c: 3}) do
    it { is_expected.to respond_to :size, :keys }
  end
end
```

```ruby
context 'using satisfy matcher' do
  describe 'racecar' do
    it { is_expected.to satisfy('be a palidrome') { |v| v.reverse == v } }
  end
end
```
