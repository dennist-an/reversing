# Dennis Reversing Guide
## Identifying type of Compression Algorithm used
## Compression Algorithms
Common compression algorithm includes
 - APLIB
 - ZLIB
 - LZMA
 - LZW
#### Identifying Compression Algorithms using Tools
signrch automate the process of searching for compression algorithm through constants.

#### API
 - NT_RTL_COMPRESSION_API

#### zlib
zlib (RFC 1950) sticks a header onto the compressed data, so seeing one of the following sequence of byte at the start of a buffer could indicate that it is zlib compressed:
```
x78 x9c
x78 xda
x78 x5e
x78 x01
```