
# Proof of Work

Proof-of-work is simply the double-sha256 of the block header. If this number, interpreted as a little-endian integer is lower than the target, we have a valid proof-of-work. If not, the block is not valid. Note that this is very easy to check. All we need to calculate is a single double-sha256 to check. On the other hand, creating the proof-of-work is really difficult. We would need to calculate on average X number of double-sha256 hashes at a difficulty of Y. This is what we would call an asymmetric problem and the reason why proof-of-work is an effective way to measure that the block producer has expended a sufficient amount of energy.

There's a reason why this process is likened to mining. It takes roughly 2-90 tons of processing dirt and rock in order to find a single ounce of gold. In the same way, we have to process lots of numerical dirt and rock in order to find a proof-of-work. Proof-of-work is rare and uniformly distributed, making finding one just as difficult with one type of header versus another.

### Try it

#### Validate the proof-of-work for this block
```
04000000fbedbbf0cfdaf278c094f187f2eb987c86a199da22bbb20400000000000000007b7697b29129648fa08b4bcd13c9d5e60abb973a1efac9c8d573c71c807c56c3d6213557faa80518c3737ec1
```

Check that the proof-of-work (double-sha256 interpreted as a little-endian number) is lower than the target.


```python
from io import BytesIO
from helper import double_sha256, little_endian_to_int
from block import Block

hex_block = '04000000fbedbbf0cfdaf278c094f187f2eb987c86a199da22bbb20400000000000000007b7697b29129648fa08b4bcd13c9d5e60abb973a1efac9c8d573c71c807c56c3d6213557faa80518c3737ec1'

# bytes.fromhex to get the binary block
# make a stream using BytesIO
# parse the Block

# double_sha256 the serialization
# interpret the result as a number in little endian
# get the target
# check proof of work < target
```

### Test Driven Exercise


```python
from io import BytesIO
from helper import double_sha256, little_endian_to_int
from block import Block

class Block(Block):
    
    def check_pow(self):
        '''Returns whether this block satisfies proof of work'''
        # get the double_sha256 of the serialization of this block
        # interpret this hash as a little-endian number
        # return whether this integer is less than the target
        pass
```
