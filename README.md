# WhatsApp Protocol / MITM Research

> Historical security research originally published in 2017.

Research code accompanying a published technical analysis of the WhatsApp
client transport protocol, its Noise-based cryptographic handshake, and a
controlled local man-in-the-middle (MITM) setup used for protocol analysis
and reverse engineering.

## Publication

**WhatsApp, что внутри?** ("WhatsApp, what's inside?")

Originally published on Habr in the Bringo engineering blog:

https://habr.com/ru/companies/bringo/articles/339224/

**Original publication: 2017-10-10**

The publication documents the protocol-analysis and reverse-engineering work
associated with this repository. This repository contains the research code
referenced by that publication.

## Research focus

The project explores:

- protocol analysis of the WhatsApp FunXMPP framing (a token-compressed XML stream);
- reverse engineering of the client connection and login flow;
- cryptographic protocol analysis (Curve25519 key agreement, AES-256-GCM, HKDF-SHA256);
- analysis of the Noise-based handshake used by the client (`Noise_XX_25519_AESGCM_SHA256`);
- controlled local man-in-the-middle experimentation on the researcher's own session;
- security research tooling written in PHP.

## Research scope

This repository contains proof-of-concept research code created for protocol
analysis, cryptographic research, and reverse engineering in a controlled
research environment.

The repository is preserved as historical security research and educational
material.

Nothing in this repository should be interpreted as authorization to test
third-party systems, infrastructure, services, or user accounts without
permission.

## Repository contents

| File | Role |
| --- | --- |
| `mitm.php` | Example entry point wiring the local server and client together. |
| `server.class.php` | Local server that emulates the WhatsApp server endpoint during the handshake. |
| `client.class.php` | Client that performs the Noise handshake and FunXMPP login flow. |
| `wacrypt.class.php` | Handshake cryptography: Curve25519, AES-256-GCM, and the key schedule. |
| `functions.php` | Helpers: logging, secure random, the SHA-256 handshake hash, and HKDF. |
| `tokenstaticmap.class.php` | FunXMPP static token dictionary used to decode the compressed XML stream. |

## Project provenance

The underlying research and accompanying code originate from the work
described in the original 2017 publication listed above.

Repository documentation (this README and the repository metadata) was added
in 2026 to make the project's scope, authorship, publication history, and
research context easier to verify. This documentation is **not** part of the
original 2017 material, and it is not presented as if it existed in 2017. The
authoritative timestamp for the documentation is the Git commit that
introduced it; the evidence of the historical date is the external Habr
publication, not Git metadata.

## Author

**Oz Kaiser**

GitHub: [@tatikoma](https://github.com/tatikoma)

The original 2017 article was published on Habr under the same author's
`Tatikoma` account.

## License

This project is licensed under the GNU General Public License v3.0.
See [LICENSE](LICENSE).
