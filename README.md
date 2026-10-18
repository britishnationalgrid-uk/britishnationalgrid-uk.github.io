# BritishNationalGrid.uk

The source and the GitHub Pages build live in this repository.

## Development

Use Node.js 22 and Yarn 1.

```sh
yarn install --frozen-lockfile
yarn dev
```

Open the local URL printed by Vite. Application code, styles, and the development HTML are in `app/`.

## Build and preview

```sh
yarn build
yarn preview
```

Vite builds into the ignored `dist/` directory, then the build script copies the production `index.html` and `assets/` to the repository root, which is the existing GitHub Pages publishing layout. It preserves the source and `CNAME`. Commit source changes and the generated build together, then push `main` to publish. Older hashed assets are retained by the build.

`CNAME` sets the custom domain to `britishnationalgrid.uk`.

## OS API branding

The official OS API Branding v0.4.0 assets are vendored at a pinned commit in
`app/public/vendor/os-api-branding/` with provenance and checksums. The deferred
script in `app/index.html` sets the statement, grid credit and OS links. The full
notice stays visible on desktop. At widths up to 480px, the original OpenLayers
information control reveals that same notice in a dismissible panel; the OS logo
remains visible. The upstream <=420px hiding rule is overridden inside the panel.

See [branding review and licensing notes](docs/os-branding.md) and the desktop
and mobile screenshots there. Change source files and run `yarn build` to update
the GitHub Pages files. Do not edit the compiled bundle or upstream artwork.

## Source recovery

Source was recovered from `/home/peter_devoy/bng-2`, last edited on 13 April 2025. It includes the later tile URL obfuscation wrapper. Before that wrapper, the source reproduced the published April 2025 build byte for byte. The older `britishnationalgrid` and `britishnationalgrid-v2` folders are earlier implementations.
