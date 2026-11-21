# lifeOS agent

lifeOS is a private app for one household of two people. Its Wishlist follows the prices of a
few products they want to buy, and tells them when one drops.

This repository publishes the public part of lifeOS's identity when it asks a store's catalog:

- [`ucp-profile.json`](ucp-profile.json): its agent profile for the
  [Universal Commerce Protocol](https://ucp.dev). It only searches and looks up products: no
  carts, checkout or orders. It carries the public key that signs lifeOS's requests
  (HTTP Message Signatures, RFC 9421, ECDSA P-256).

At a store, lifeOS makes a few catalog searches and product lookups a day, for the products the
household follows. It backs off on `429` and honours `Retry-After`. It never adds to a cart or
buys anything.

Questions, or a store that wants it to stop: open an issue in this repository.
