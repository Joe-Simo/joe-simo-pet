# Joe Simo Pet

Premium-polished Codex pet package for Joseph Simo.

Install Joe's animated Codex pet in one terminal command, or copy the prompt below to ask Codex to make a custom pet from your own picture.

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

## Quick Install

Paste this into a terminal to install the pet without cloning the repo:

```sh
PET_DIR="$HOME/.codex/pets/simo-real"
mkdir -p "$PET_DIR"
curl -fsSL "https://raw.githubusercontent.com/Joe-Simo/joe-simo-pet/main/pet/pet.json" -o "$PET_DIR/pet.json"
curl -fsSL "https://raw.githubusercontent.com/Joe-Simo/joe-simo-pet/main/pet/spritesheet.webp" -o "$PET_DIR/spritesheet.webp"
echo "Installed Joe Simo Pet at $PET_DIR"
```

Restart Codex if it was already open.

## Manual Install

If you cloned this repository, install it with:

```sh
mkdir -p "$HOME/.codex/pets/simo-real"
cp pet/pet.json "$HOME/.codex/pets/simo-real/pet.json"
cp pet/spritesheet.webp "$HOME/.codex/pets/simo-real/spritesheet.webp"
```

## Make Your Own Codex Pet

Paste this prompt into Codex and attach your picture, or replace the image path with the absolute path to a local image:

```text
Use the hatch-pet skill to make a Codex pet from my own picture.

Picture: <attach my image here, or use /absolute/path/to/my-picture.png>
Pet name: <my pet name>
Style: auto. Preserve the recognizable face, silhouette, colors, and personality from the picture, but make it readable as a small animated Codex pet.

Create a complete Codex-compatible pet package with:
- pet.json
- spritesheet.webp
- all required animation states: idle, running-right, running-left, waving, jumping, failed, waiting, running, review
- contact sheet and preview images for visual QA
- validation results for atlas size, transparency, unused cells, duplicate frames, and frame readability

Install the finished pet locally at:
~/.codex/pets/<safe-pet-id>

Keep it public-safe. Do not put my original private picture, credentials, API keys, or unrelated project files into the final package or repository.
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
