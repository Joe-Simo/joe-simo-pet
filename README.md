# Joe Simo Pet

Premium-polished Codex pet package for Joseph Simo.

This repository is intentionally small and public-safe. It contains only the pet package, preview images, and validation artifacts. It does not include the `joesimo` personal website project, source website files, API code, credentials, or private source portraits.

## Contents

- `pet/pet.json` - Codex pet metadata.
- `pet/spritesheet.webp` - Codex-compatible animated pet atlas.
- `preview/` - contact sheets and visual QA previews.
- `checks/` - validation and frame-audit JSON from the final installed package.

## Pet Specs

- Atlas size: `1536x1872`
- Cell size: `192x208`
- States: `idle`, `running-right`, `running-left`, `waving`, `jumping`, `failed`, `waiting`, `running`, `review`
- Final installed hash: `84e15464f37409b798c2e59c5699540993acc98952c855c23737e1b8406c1e62`

## Preview

![Joe Simo pet contact sheet](preview/contact-sheet.png)

## Install Locally

To install as a Codex pet on a local machine:

```sh
mkdir -p "$HOME/.codex/pets/simo-real"
cp pet/pet.json "$HOME/.codex/pets/simo-real/pet.json"
cp pet/spritesheet.webp "$HOME/.codex/pets/simo-real/spritesheet.webp"
```

## Validation Summary

The final installed package passed:

- `1536x1872` RGBA WebP atlas validation
- `0` transparent RGB residue pixels
- `0` exact duplicate frames
- `0` nontransparent unused-cell pixels
- `0` large disconnected alpha-component anomalies
- `0.0%` blueish pixels in the face-only mouth-color review

## License

MIT. See `LICENSE`.
