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
* Dilithium, HSS, Kyber, Rainbow, XMSS - `anne-of-green-gables.epub` used as
  the message.
* HSS and XMSS keys were all generated using the BDS tree strategy (called the
  "Memory Constrained" strategy since Toolkit 2.0).
* Poly1305 - `anne-of-green-gables.ebub` used as the message.

The Diffie-Hellman-like algorithms (FrodoDH, LUKE, NewHopeDH, and SIDH) and key
encapsulation mechanisms (Frodo KEM, McEliece QC-MDPC, NTRUPrime, and SIKE)
don't require additional inputs.

## Known Issues

Known interoperability issues will be documented here, along with explanations.

### 1.5 to 2.0

Changes:

* HSS parameters were changed from specifying Winternitz and Height to choosing
  from optimal variants; see the [2.0 notes](2.0/README.md) for a mapping to
  the 1.5 parameters.
* HSS/XMSS tree strategies were renamed (and new ones added); the "BDS"
  strategy from 1.5 is now known as "Memory Constrained" in 2.0.

Incompatibilities:

* NTRUPrime private keys are not compatible between 1.5 and 2.0.
* Rainbow private keys are not compatible between 1.5 and 2.0.
* Algorithms present in
  [Round 2](https://csrc.nist.gov/projects/post-quantum-cryptography/round-2-submissions)
  of the NIST Post-Quantum Cryptography competition had their variants updated
  between 1.5 and 2.0 to match the Round 2 versions. Artifacts for these
  algorithms are not compatible between 1.5 and 2.0.
* FrodoDH was updated to match the FrodoKEM variants from NIST's competition.
  Its artifacts are not compatible between 1.5 and 2.0.
* SIDH was updated to match the SIKE variants from NIST's competition. Its
  artifacts are not compatible between 1.5 and 2.0.

New algorithms:

* Samwise - An ISARA optimized variant of FrodoDH.
* SPHINCS+ - A stateless hash-based digital signature scheme from the NIST
  competition.
* XMSS<sup>MT</sup> - The multi-tree version of XMSS.

Removed algorithms:

* LUKE - An ISARA optimized variant of NewHope.
* McEliece QC-MDPC KEM - An ISARA designed KEM.

## License

These are released under the Apache 2.0 license. See `LICENSE` for details.
