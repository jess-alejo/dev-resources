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