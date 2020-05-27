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

## Known Issues

Known interoperability issues will be documented here, along with explanations.

## License

These are released under the Apache 2.0 license. See `LICENSE` for details.
