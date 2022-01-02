# brotli-js

compressor and decompressor for Brotli in Javascript, retrofit based on this [repo](https://github.com/dominikhlbg/brotlijs), supporting `node` and `browser`

## Installation and usage

    npm i brotli-js -S

```javascript
const brotli = require('brotli-js')

const str = 'test txt'
const buf = new ArrayBuffer(str.length)
const bufView = new Uint8Array(buf)

for (let i = 0, strLen = str.length; i < strLen; i++) {
  bufView[i] = str.charCodeAt(i)
}

const compressed = brotli.compressArray(bufView, 6)
const decompressed = brotli.decompressArray(compressed)
const restoredStr = String.fromCharCode.apply(null, decompressed)
```

## API

### brotli.compressArray(buffer, level)

Decompresses the given buffer to produce the original input to the compressor.
The `level` parameter accept 0 - 11

```javascript
brotli.compressArray(bufView, 6)
```

### brotli.decompressArray(buffer)

Compresses the given buffer.

```javascript
brotli.decompressArray(compressedData)
```
