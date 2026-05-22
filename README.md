# Daena Examples

Real, signed Daena documents for real things. Copy them, adapt them, learn from them.

Every example here is a valid Daena document against the [current spec draft](https://github.com/daena-protocol/spec/blob/main/SPEC.md). Each example folder contains:

- `daena.json` — the document itself, with a real ed25519 signature
- `did.json` — the publisher's DID document with the matching public key
- `README.md` — a short walkthrough including the verification command

Every example verifies end-to-end:

```bash
daena validate --verify daena.json --did-doc did.json
```

## Index

| Vertical | Example | What it shows |
|---|---|---|
| Restaurant | [`restaurants/pho-saigon`](./restaurants/pho-saigon) | Menu, hours, dietary tags, reservation capability, real ed25519 signature |
| *(more coming)* | | |

## Contributing an example

We especially welcome examples in verticals where the human web is most broken: government services, healthcare information, education, public transit, public records.

Open a PR adding a new folder under the relevant vertical, with `daena.json`, `did.json`, and `README.md`. The example must verify against its companion DID document.

## License

Examples are released under [CC0](./LICENSE) so anyone can copy them freely.
