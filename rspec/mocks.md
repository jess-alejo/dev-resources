### Mocks
A double is a mock object that stands in for a real object in a test suite.

```ruby
context 'mocks' do
  describe 'double' do
    it 'defines methods using initializer' do
      stuntman = double('Mr. Danger', jump_from_plane: 'Oh no!', head_first: true)

      expect(stuntman.jump_from_plane).to eq 'Oh no!'
      expect(stuntman.head_first).to be true
    end

    it 'allows receiving method and returning values' do
      stuntman = double('Mr. Danger')
      allow(stuntman).to receive(:jump_from_plane).and_return('Oh no!')
      allow(stuntman).to receive(:head_first).and_return(true)

      expect(stuntman.jump_from_plane).to eq 'Oh no!'
      expect(stuntman.head_first).to be true
    end

    it 'allows receiving messages' do
      stuntman = double('Mr. Danger')
      allow(stuntman).to receive_messages(jump_from_plane: 'Oh no!', head_first: true)

      expect(stuntman.jump_from_plane).to eq 'Oh no!'
      expect(stuntman.head_first).to be true
    end
  end
end
```

Customize the return value of a stubbed method depending on the argument or arguments which invoked the method

```ruby
describe 'matching arguments' do
  it 'can return different values depending on the arguments' do
    three_element_array = double # [1, 2, 3]

    allow(three_element_array).to receive(:first).with(no_args).and_return(1)
    allow(three_element_array).to receive(:first).with(1).and_return([1])
    allow(three_element_array).to receive(:first).with(2).and_return([1, 2])
    allow(three_element_array).to receive(:first).with(3).and_return([1, 2, 3])
    allow(three_element_array).to receive(:first).with(be >= 3).and_return([1, 2, 3])

    expect(three_element_array.first).to eq 1
    expect(three_element_array.first 1).to eq [1]
    expect(three_element_array.first 2).to eq [1, 2]
    expect(three_element_array.first 3).to eq [1, 2, 3]
    expect(three_element_array.first 100).to eq [1, 2, 3]
  end
end
```
