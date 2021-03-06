
# curve25519-dalek ![](https://img.shields.io/crates/v/curve25519-dalek.svg) ![](https://docs.rs/curve25519-dalek/badge.svg)

**A low-level cryptographic library for point, group, field, and scalar
operations on a curve isomorphic to the twisted Edwards curve defined by -x²+y²
= 1 - 121665/121666 x²y² over GF(2²⁵⁵ - 19).**

**SPOILER ALERT:** *The Twelfth Doctor's first encounter with the Daleks is in
his second full episode, "Into the Dalek". A beleaguered ship of the "Combined
Galactic Resistance" has discovered a broken Dalek that has turned "good",
desiring to kill all other Daleks. The Doctor, Clara and a team of soldiers
are miniaturized and enter the Dalek, which the Doctor names Rusty. They
repair the damage, but accidentally restore it to its original nature, causing
it to go on the rampage and alert the Dalek fleet to the whereabouts of the
rebel ship. However, the Doctor manages to return Rusty to its previous state
by linking his mind with the Dalek's: Rusty shares the Doctor's view of the
universe's beauty, but also his deep hatred of the Daleks. Rusty destroys the
other Daleks and departs the ship, determined to track down and bring an end
to the Dalek race.*

Significant portions of this code are ported from [Adam Langley's
Golang ed25519 library](https://github.com/agl/ed25519), which is in
turn a port of the reference `ref10` implementation.

## Warning

This code has **not** yet received sufficient peer review by other qualified
cryptographers to be considered in any way, shape, or form, safe.  Further,
this library does **not** provide high-level routines such as encryption and
decryption or signing and verification.  Instead, it is a low-level library,
intended for other cryptographers who would like to implement their own
primitives using this curve.  (For an example of how one would implement a
signature scheme using this library, see
[ed25519-dalek](https://github.com/isislovecruft/ed25519-dalek).)

**USE AT YOUR OWN RISK**

## Documentation

Extensive documentation is available [here](https://docs.rs/curve25519-dalek).

# Installation

To install, add the following to the dependencies section of your project's
`Cargo.toml`:

    curve25519-dalek = "^0.5"

Then, in your library or executable source, add:

    extern crate curve25519_dalek

## TODO

* Implement hashing to a point on the curve (Elligator).
* Add conversion to Montgomery form and rework compressed point types.
* Maybe implement Mike Hamburg's Decaf point compression format, so that
  users can be guaranteed to be in a prime-order subgroup and not have to
  worry about cofactors.
* Review finite field arithmetic.
* Review scalar arithmetic.
* Review addition formulas.
* Proofread mathematics in documentation.
* Maybe use serde for serialization.
