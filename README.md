# Artifacts from ISARA's Toolkit

Keys, digital signatures, etc. created with the ISARA Radiate Quantum-safe
Library.

Use these artifacts to test interoperability between ISARA's implementations
and yours, and between versions.

For information about the ISARA Radiate Quantum-safe Toolkit, please
visit [our website](https://www.isara.com/products/isara-radiate.html).

## Organization

The artifacts are organized by release version, platform endianness, and
algorithm. For example:

* `1.5/le/dilithium` - Keys and signatures from version 1.5 of our Dilithium
  implementation, generated on a little-endian (x86-64) machine.
* `2.0/be/rainbow` - Keys and signatures from version 2.0 of our Rainbow
  implementation, generated on a big-endian (PowerPC) machine.

See individual `README.md` files inside the directories for details.

### Additional Files

The ePub version of L. M. Montgomery's
[Anne of Green Gables](https://www.gutenberg.org/ebooks/45) in
`anne-of-green-gables.epub` was used as a data source any time a message
was required (for signatures, as an input to symmetrical cryptography, etc.).

`aead-chacha20.aad` is additional authenticated data used for the AEAD ChaCha20
Poly1305 artifacts, specified with `--aad` in the AEAD samples.

`chacha20.key` is a 256-bit key used to encrypt the ChaCha20 artifacts
(including the AEAD ChaCha20 Poly1305 artifacts).

`chacha20.nonce` is a 96-bit nonce used to encrypt the ChaCha20 artifacts
(including the AEAD ChaCha20 Poly1305 artifacts).

`poly1305.key` is a 256-bit key used to MAC the Poly1305 artifacts.

### Artifact Generation

* AEAD ChaCha20 Poly1305 - `anne-of-green-gables.epub` encrypted using
  `chacha20.key`, the `chacha20.nonce`, and `aead-chacha20.aad` as additional
  authenticated data.
* ChaCha20 - `anne-of-green-gables.epub` encrypted using `chacha20.key`, the
  `chacha20.nonce`, and starting an initial counter of 0.
* HSS keys were all generated using the BDS tree strategy (called the "Memory
  Constrained" strategy since Toolkit 2.0.

## Known Issues

Known interoperability issues will be documented here, along with explanations.

## License

These are released under the Apache 2.0 license. See `LICENSE` for details.
