# MySQL Pro Client 2.4.0 — Visual Foreign Key Designer

## Headline
Design MySQL relationships visually without writing FOREIGN KEY syntax by hand.

## Highlights

- Live schema, table and column selectors.
- Simple and composite foreign keys.
- Ordered local → referenced column mappings.
- ON DELETE / ON UPDATE controls.
- Referenced index-prefix validation.
- SET NULL nullability safety.
- Existing FK editing and self-referencing relationships.
- SQL Preview remains mandatory before Apply Changes.

## Release gate

```bash
npm install
npm run verify
```

Then test with F5 and package:

```bash
npm run package:release
```

Expected artifact: `mysql-pro-client-2.4.0.vsix`.
