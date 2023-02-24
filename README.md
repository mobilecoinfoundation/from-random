# MobileCoin: A trait for constructing an object from an CSPRNG

[![Project Chat][chat-image]][chat-link]<!--
-->![License][license-image]<!--
-->![Architecture: any][arch-image]<!--
-->[![Crates.io][crate-image]][crate-link]<!--
-->[![Docs Status][docs-image]][docs-link]<!--
-->[![Dependency Status][deps-image]][deps-link]<!--
-->[![CodeCov Status][codecov-image]][codecov-link]<!--
-->[![GitHub Workflow Status][gha-image]][gha-link]<!--
-->[![Contributor Covenant][conduct-image]][conduct-link]

A trait for constructing an object from an CSPRNG.

## Example

```rust
use mc_from_random::{CryptoRng, FromRandom, RngCore};

struct MyStruct {
    pub bytes: [u8; 32],
}

impl FromRandom for MyStruct {
    fn from_random<R: CryptoRng + RngCore>(csprng: &mut R) -> Self {
        MyStruct {
            bytes: <[u8; 32]>::from_random(csprng),
        }
    }
}
```

[chat-image]: https://img.shields.io/discord/844353360348971068?style=flat-square
[chat-link]: https://mobilecoin.chat
[license-image]: https://img.shields.io/crates/l/mc-from-random?style=flat-square
[arch-image]: https://img.shields.io/badge/arch-any-brightgreen?style=flat-square
[crate-image]: https://img.shields.io/crates/v/mc-from-random.svg?style=flat-square
[crate-link]: https://crates.io/crates/mc-from-random
[docs-image]: https://img.shields.io/docsrs/mc-from-random?style=flat-square
[docs-link]: https://docs.rs/crate/mc-from-random
[deps-image]: https://deps.rs/repo/github/mobilecoinfoundation/from-random/status.svg?style=flat-square
[deps-link]: https://deps.rs/repo/github/mobilecoinfoundation/from-random
[codecov-image]: https://img.shields.io/codecov/c/github/mobilecoinfoundation/from-random/develop?style=flat-square
[codecov-link]: https://codecov.io/gh/mobilecoinfoundation/from-random
[gha-image]: https://img.shields.io/github/workflow/status/mobilecoinfoundation/from-random/ci.yaml?branch=main&style=flat-square
[gha-link]: https://github.com/mobilecoinfoundation/from-random/actions/workflows/ci.yaml?query=branch%3Amain
[conduct-link]: CODE_OF_CONDUCT.md
[conduct-image]: https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg?style=flat-square
