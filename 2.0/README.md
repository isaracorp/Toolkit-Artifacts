# Toolkit 2.0 Artifacts

These artifacts were generated by
[Toolkit release 2.0](https://www.isara.com/toolkit/2.0/README.html).

## HSS Parameter Mapping

In 2.0, we redesigned the HSS API to make it easier to choose optimal parameter
sets.

|2.0 Variant|1.5 Winternitz (W)|1.5 Height (H)|
|-----------|------------------|--------------|
|2e20 Fast  |2                 |20            |
|2e20 Small |8                 |20            |
|2e25 Fast  |2                 |25            |
|2e25 Small |8                 |25            |

## Rainbow Parameter Mapping

In 2.0, we removed several Rainbow variants and renamed the rest to better
match their parameters.

Removed variants: IIIb, IVa, VIa, VIb.

|2.0 Variant         |1.5 Variant|
|--------------------|-----------|
|GF(256), 68, 36, 36 |IIIc       |
|GF(256), 92, 48, 48 |Vc         |