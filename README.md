# Joe Simo Pet

Premium-polished example Codex pet package for Joseph Simo.

Use this as an example package, or copy the prompt below to ask Codex to make a custom pet from your own face or picture.

This repository is intentionally small and public-safe. It contains only the pet package, preview images, and validation artifacts. It does not include the `joesimo` personal website project, source website files, API code, credentials, or private source portraits.

## Copy-Paste Prompt

Paste this into Codex and attach a clear picture of your face, pet, mascot, or character:

```text
Use the hatch-pet skill to make my own Codex pet from my attached picture.

Use my picture as the identity source, not Joe Simo's pet. Preserve the recognizable face, silhouette, colors, expression, and personality from my picture, but simplify it into a compact animated Codex pet that reads clearly at small size.

Pet name: <my pet name>
Style: auto, based on my picture
Install location: ~/.codex/pets/<safe-pet-id>

Create a complete Codex-compatible pet package with:
- pet.json
- spritesheet.webp
- all required animation states: idle, running-right, running-left, waving, jumping, failed, waiting, running, review
- contact sheet and preview images for visual QA
- validation results for atlas size, transparency, unused cells, duplicate frames, and frame readability

Keep it public-safe. Do not include my original picture, private files, credentials, API keys, or unrelated project files in the final package or any repository.
```

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

## Install Joe's Example Pet

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

## Custom Pet Prompt With Image Path

If your picture is already saved locally, paste this into Codex and replace the image path:

```text
Use the hatch-pet skill to make my own Codex pet from my picture.

Picture: <attach my image here, or use /absolute/path/to/my-picture.png>
Pet name: <my pet name>
Style: auto. Preserve the recognizable face, silhouette, colors, and personality from the picture, but make it readable as a small animated Codex pet.

Use my picture as the identity source, not Joe Simo's pet.

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
