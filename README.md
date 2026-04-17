# Retro Gaming Retrospective: Castlevania Across Three Platforms

> *A visual hardware analysis of Colour Palettes and Tile & Sprite Sizing across the NES, Game Boy, and SNES — and a look at how far the series has come.*

---

## Introduction

Personally, I am not a huge gamer — the only retro game I had played before this project was Pac-Man. While researching options, I came across Castlevania and immediately fell in love with the series. It felt like the inverse of my favourite movie series, *Hotel Transylvania*.

What I didn't expect was how dramatically the visuals would differ across the three versions. That became the focus of this retrospective: **what does the game look like, and why does it look so different on each platform?**

The NES, Game Boy, and SNES each have hard limits on colour count, sprites per scanline, and video memory. Those constraints show up directly on screen — and Castlevania makes them *very* visible, because the same castle, the same enemies, and the same character have to be drawn within completely different rules on each system.

---

## Focus Areas

| Focus | Description |
|---|---|
| **Colour Palettes** | How each platform handles colour limitations and how that affects mood and visual detail |
| **Tile & Sprite Sizing** | Differences in tile dimensions used to build characters and environments, and how this impacts animation |

---

## Games Covered

| Platform | Game | Year | Notes |
|---|---|---|---|
| **NES** | *Castlevania* | 1987 | The original. Simon Belmont, a whip, a castle, and Dracula. |
| **Game Boy** | *Castlevania: The Adventure* | 1989 | First portable entry, released the same year as the Game Boy itself. |
| **SNES** | *Super Castlevania IV* | 1991 | The 16-bit reimagining. Widely considered one of the best games on the system. |

---

## Title Screens Across All Three Platforms

> Here you can see the title screen rendered on each of the three devices side by side.

![Title Screen Comparison](https://github.com/user-attachments/assets/f450bce7-5d5a-4ecc-8df9-230bce3f7b83)

---

## Part 1 — Colour Palettes

### NES — *Castlevania* (1987)

<img align="right" width="180" src="https://github.com/user-attachments/assets/6c972394-1151-4f8c-8a0f-68e50ad56951" />

**Hardware Specs**
- **Resolution:** 256×240 pixels
- **PPU:** Ricoh 2C02
- **Total palette:** 54 colours (25 usable simultaneously)
- **Background slots:** 13 colours (four 3-colour sub-palettes + 1 shared background)
- **Sprite slots:** 12 colours (four 3-colour sub-palettes + transparency)
- **Source:** [Carleton University SCS Vintage Computing Collection — VIN155](https://carleton.ca/scs/vintage-computing/item/vin155/)

**What I played:** `Castlevania (USA).nes` — loaded into FCEUX, launched from the terminal. I died repeatedly in Stage 1 and barely saw Stage 2.

<br clear="right"/>

---

#### Title Screen Analysis

![NES Title Screen](https://github.com/user-attachments/assets/ae917bfa-c88d-4016-9f35-e4dce0b93879)

The title screen uses only **10 colours**, rendered entirely as a single background layer. This is below even the theoretical 13-colour background maximum — the artists deliberately self-limited to avoid visual clashing at the mandatory **16×16 pixel attribute grid** borders. The 12 additional sprite-palette colours remain completely inaccessible here, since no active sprites are present on the title screen.

> *The theoretical maximum of 25 simultaneous colours on the NES is only achievable when both the background layer and active sprites are drawing at the same time.*

---

#### Gameplay Analysis

![NES Gameplay](https://github.com/user-attachments/assets/d4c0e132-a49a-40ad-98eb-ed27cdbeb3cc)

The setting palette leverages the NES's background limitations to create a somber, gothic atmosphere:

- **Deep blues and blacks** → moonlit night sky
- **Vibrant greens and oranges** → foreground foliage and structures
- **Dithering (checkerboard pixel patterns)** → simulates gradients and stone wall textures where smooth colour transitions would otherwise be impossible

Because the background is restricted to four 3-colour palettes, artists used dithering to fake gradients — once you notice it, you see it everywhere in the castle walls.

![NES Gameplay 2](https://github.com/user-attachments/assets/d4c0e132-a49a-40ad-98eb-ed27cdbeb3cc)

---

#### Simon Belmont — Sprite Design

![Simon NES](https://github.com/user-attachments/assets/278fc135-4002-45c0-8f5b-d49a614b019b)

Simon Belmont's sprite is a tiny miracle of NES-era problem-solving. Three colours — tan, brown, and bold red — carry the entire character design.

Key techniques used:

- **Open outlining** — the castle's black background bleeds into the silhouette to fake extra detail in his hair and boots
- **High contrast** — his red tunic against cool blue environments works almost theatrically, constantly spotlighting the player
- **Separate whip sprite** — the whip is its own sprite on its own palette, which is why it can flash pale purples and whites without breaking the three-colour limit per sprite

> *The whip being a separate sprite was genuinely surprising to me — it explains so much about how the colour flashing works.*

---

### Game Boy — *Castlevania: The Adventure* (1989)

<img align="right" width="180" src="https://github.com/user-attachments/assets/be3cc3e3-2c1e-44fd-b3a6-ca05dc2f7f12" />

**Hardware Specs**
- **Resolution:** 160×144 pixels
- **Palette:** Exactly 4 shades of grey (no colour)
- **Display:** Green-tinted LCD — the image appears slightly olive rather than true black-and-white
- **Transparency:** One shade per sprite palette must be reserved for transparency
- **Source:** [Copetti, *Game Boy / Color Architecture*](https://www.copetti.org/writings/consoles/game-boy/)

**What I played:** `Castlevania - The Adventure (USA).gb` — loaded into mGBA. Found it easier to survive than the NES version, but it felt stripped down.

<br clear="right"/>

---

#### Title Screen Analysis

![GB Title Screen](https://github.com/user-attachments/assets/9fd831ff-73a6-400f-8940-14c779118cd8)

The Game Boy title screen operates under a strict four-shade monochrome palette, forcing Konami to abandon colour variety entirely in favour of extreme pixel-level detail.

- **Advanced dithering** (checkerboard + stippling patterns) simulates textured stone and complex shading within the logo
- The design achieves a *grittier, more weathered* appearance than its NES predecessor
- High-density side scenery is sacrificed to focus memory on **sharp, legible typography**
- Maximum contrast (darkest black vs. lightest white) ensures readability on the small, non-backlit screen

---

#### Gameplay Analysis

![GB Gameplay](https://github.com/user-attachments/assets/9fd831ff-73a6-400f-8940-14c779118cd8)

The four-shade palette is pushed to its limit to create depth without colour:

| Layer | Shade Strategy |
|---|---|
| Sky (background) | Lightest shade |
| Mid-ground trees | Mid-tones with heavy vertical dithering to simulate bark texture |
| Christopher + enemies | Darkest blacks — kept distinct from background |

Unlike the NES, which used distinct hues to separate objects, the Game Boy relies on the **same four shades across every element**. Sprites and background tiles share an identical palette, which means the hero and enemies frequently blend into the environment. Where the NES used a bold red to make Simon pop instantly, the Game Boy must rely on thick outlines alone.

---

#### Christopher Belmont — Sprite Design

![Christopher GB](https://github.com/user-attachments/assets/91500965-01b3-49e7-99ba-202bb723dc68)

Christopher's design was a calculated response to the Game Boy's **motion blur** and **low contrast**. The screen's slow refresh rate turns fine internal lines into an unreadable smudge in motion, so Konami employed *"safety simplicity"*:

- **Solid blocks of light grey** instead of fine internal detail
- **Thick, dark-black outlines** maintain a clear silhouette regardless of motion
- **"Palette flattening"** — only the extreme shades (lightest and darkest) are used, bypassing the muddy middle-grey values entirely

The result is a flat, paper-cutout appearance. The character often visually merges with the background since both share the same limited four shades — the thick black outline is the *only consistent anchor* against environmental detail.

---

### SNES — *Super Castlevania IV* (1991)

**Hardware Specs**
- **Simultaneous colours:** 256 from a master palette of 32,768
- **PPU:** Two dedicated PPU chips
- **Capabilities:** Colour blending, gradients, and transparency effects impossible on earlier hardware
- **Source:** [Copetti, *Super Nintendo / Famicom Architecture*](https://www.copetti.org/writings/consoles/super-nintendo/)

**What I played:** `Super Castlevania IV` — loaded into Snes9x. Made it through the first several stages.

---

#### Title Screen Analysis

![SNES Title Screen](https://github.com/user-attachments/assets/f837e242-a9a7-4e7c-9715-40d9dda05aee)

The jump to 256 simultaneous colours removes every restriction that defined the earlier entries:

- **Complex gradients** on the stone wall use dozens of variations of purple, grey, and green — completely impossible on the NES's 13-background-colour limit
- **Hardware alpha blending** via the dual PPUs produces smooth transparency and lighting effects
- Vines and the metallic logo feel **tactile and three-dimensional**, a stark contrast to the flat dithering of the Game Boy or the simplified colour blocks of the NES

---

#### Gameplay Analysis

![SNES Gameplay](https://github.com/user-attachments/assets/b8c32744-31c2-4721-a71b-2e9f15ccb3c1)

Super Castlevania IV uses every capability of the dual PPU system:

- **Sub-palette mixing** creates a seamless deep purple-to-black sky gradient, free from the "staircase" banding of NES attribute limits
- **16 colours per tile** allows artists to layer dozens of grey and green values within a single 8×8 block, producing organic stone and decaying moss textures
- **Hardware-level alpha blending** on hanging vines and the distant skull produces a translucent fog effect by mathematically averaging overlapping layer values

---

#### Simon Belmont — SNES Sprite Design

![Simon SNES](https://github.com/user-attachments/assets/29eb7743-e51f-47ad-bc98-2f46cc289d8e)

The SNES design represents a fundamental shift in what a sprite *can be*:

- **Full 16-colour palette** with colour ramping simulates the glint of moonlight on metallic armour and leather through specular highlights — impossible under NES "palette poverty"
- **Anti-aliased shading** and warm-to-cool hue contrast replaces the thick safety outlines required on the Game Boy
- **The whip** is no longer a solid-coloured overlay — it's a complex, multi-jointed object with its own colour depth, enabling fluid motion and metallic textures that would have caused severe hardware flickering on previous systems

---

### Colour Palettes — Final Comparison

| Category | NES | Game Boy | SNES |
|---|---|---|---|
| **Title Screen — Colour Count** | 10 colours (background layer only; no active sprites) | 4 shades of grey (monochrome only) | Hundreds of variations from the 256-simultaneous palette |
| **Title Screen — Key Technique** | Self-limited to 10 colours to avoid attribute grid clashing | Advanced dithering (checkerboard + stippling) simulates stone texture without hue | Smooth gradients, hardware alpha blending, translucent fog |
| **Gameplay — Key Limitation** | Hard colour boundaries at every 16×16 attribute block | All elements share the same four greys — sprites frequently blend into mid-ground tiles | None meaningful; hardware alpha blending produces fully translucent layers |
| **Gameplay — Mood** | Clear, readable depth; each layer identifiable at a glance | Texture-heavy but flat; depth comes from outline weight, not colour | Volumetric and atmospheric; the environment feels three-dimensional for the first time in the series |
| **Main Character — Colours Used** | 3 colours (tan, brown, red) + transparency | 2 effective shades (light grey + black), bypassing muddy middle greys | Full 16-colour palette with specular colour ramping |
| **Main Character — Weapon** | Separate sprite on its own palette (light purple + white) to avoid exceeding the 3-colour limit | Simplified to match the constrained character palette | Multi-jointed object with its own colour depth — fluid motion and metallic texture without hardware flickering |

---

### Modern Comparison — *Castlevania: Belmont's Curse* (PS5 / Xbox Series X / PC)

![Belmont's Curse](https://github.com/user-attachments/assets/1c35e215-87dc-463c-91b2-530a2225e203)

*Castlevania: Belmont's Curse* operates under no hardware colour constraints whatsoever — running on modern platforms with access to a full **32-bit HDR colour space** and effectively unlimited simultaneous colours.

What's striking is that Evil Empire *chose* to build the game's visual identity around a near-monochromatic fire palette anyway — flooding roughly 85% of the frame with deep ambers, burnt siennas, and saturated oranges, while reserving cool accent colours (a brief teal on an enemy, a lone blue-purple glyph) for maximum contrast.

This is a **purely artistic constraint, not a technical one**, and it stands in sharp contrast to every retro entry:

| Hardware | Constraint |
|---|---|
| NES | ~25 simultaneous colours, hard tile-based palettes |
| Game Boy | 4 shades of grey |
| SNES | Up to 256 colours, hand-dithered gradients |
| Modern | Unlimited — constraint is *chosen*, not imposed |

The warm glow, soft bloom, and translucent ember particles in *Belmont's Curse* would have been completely unachievable on any of that hardware. Evil Empire uses the full power of a modern renderer to *simulate* the atmospheric warmth of a torch-lit CRT screen — evoking the visual soul of classic Castlevania while being technically worlds apart from it.

---

## Part 2 — Tile & Sprite Sizing

### NES

**Hardware:** The Ricoh 2C02 PPU renders everything from a single fundamental unit: the **8×8 pixel tile**. Every background, wall, and floor is assembled from these fixed blocks, stored in Pattern Tables (CHR).

- Each tile costs **16 bytes** across two bitplanes, giving each pixel one of four values indexed into a colour sub-palette — [NESDev Wiki: PPU Pattern Tables](https://www.nesdev.org/wiki/PPU_pattern_tables)
- Backgrounds are laid out on a **32×30 nametable** (960 tiles mapping exactly to the 256×240 screen)
- Colour is assigned per **2×2 tile group** via the Attribute Table — colour boundaries are locked to 16-pixel intervals, and two adjacent tiles sharing an attribute cell cannot be coloured independently — [NESDev Wiki: PPU Nametables](https://www.nesdev.org/wiki/PPU_nametables)

---

#### Tile Breakdown

![NES Tile Grid](https://github.com/user-attachments/assets/c5afa52c-45df-4525-8945-df7999abb698)

![NES Tile Analysis](https://github.com/user-attachments/assets/b0941c60-bbc7-4345-ad03-4c04316d73ee)

| Element | Size | Notes |
|---|---|---|
| **Simon Belmont** | ~16×32 px (2×4 tiles) | Two stacked 8×16 hardware sprite columns — you can feel the upper/lower body split in the animation |
| **Flame/branch effect** | ~16×16 px (2×2 tiles) | Intentionally small to stay within the 8-sprites-per-scanline limit; smaller effects don't compete with Simon |
| **Tree canopy** | Variable (repeating 8×8 tiles) | Looks organic but repeats with slight variation — the repetition becomes a *texture* rather than something you notice as tiles |
| **Brick wall & ground** | 16×16 metatile groupings (2×2 blocks of 8×8) | Classic NES memory-saving design — the wall feels detailed but is really just clever reuse and placement |
| **HUD** | Full strip of 8×8 tiles (static) | Separate from the scrolling playfield; shrinks vertical space but reinforces the underlying grid structure |

Color per sprite is tightly controlled at 3 colours + transparency. Simon's palette is chosen so he always pops against the darker greens and blacks of the background — a case where limitations actually force better design, since his silhouette stays instantly readable even in motion.

---

### Game Boy

**Hardware:** The Game Boy PPU uses a strictly tile-based approach, identical to the NES in using **8×8 pixel tiles** for all background and window layers. Its Object Attribute Memory (OAM) allows two sprite sizes: **8×8 or 8×16 pixels**.

- Tracks up to **40 total sprites per frame**
- Hard limit of **10 sprites per horizontal scanline** — slightly more generous than the NES's 8, relative to its smaller 160×144 resolution
- Source: [Pan Docs — OAM: Object Attribute Memory](https://gbdev.io/pandocs/OAM.html)

---

#### Tile Breakdown

![GB Tile Analysis](https://github.com/user-attachments/assets/d61908d9-0a66-491b-b084-e731594cb87c)

| Element | Size | Notes |
|---|---|---|
| **Christopher Belmont** | ~16×32 px (4×4 tiles) | Two stacked 8×16 OBJ slots — dashed line through the middle marks the upper/lower hardware split |
| **Gift candles** | ~16×24 px (2×3 tiles) | Smaller enemy sprites leave more of the 10-sprites-per-scanline budget for the player, reducing flicker risk |
| **Dithered mist band** | 8×8 tiles | The most visually interesting technique — alternating light/dark pixels in a checkerboard pattern simulate a mid-tone gradient the hardware doesn't technically have |
| **Wall & floor** | 16×16 metatile groups (2×2 blocks of 8×8) | Standard GB tile reuse strategy to keep CHR ROM small |
| **HUD (top + bottom)** | 1 full tile row each | Squeezes the actual playfield down to just **16 usable tile rows (128 px)** |

---

### SNES

Simon's sprite sits around a **3×5 to 4×5 tile footprint (~24×40 px or larger depending on frame)**. Still built from 8×8 tiles — but the SNES allows far more sprites on screen with better composition, so the seams are much harder to notice. The character starts to feel less like stacked blocks and more like a cohesive illustration.

| Element | Size | Notes |
|---|---|---|
| **Simon Belmont** | ~24×40 px (3×5 to 4×5 tiles) | 16-colour palette with colour ramping; seams between tile sections are nearly invisible |
| **Whip** | Variable (curved arc of 8×8 tiles) | No longer a straight chain — a curved series of sprite tiles taking advantage of flexible positioning and more sprites-per-scanline |
| **Skeleton enemy** | ~4×5 tiles or more | Benefits from SNES's 128 total sprites / 32 per scanline (vs. NES's strict limits); far more presence on screen without flicker |
| **Background tiles** | 8×8 tiles grouped into 16×16 or 32×32 metatiles | Expanded colour palette means tiles can include gradients and subtle shading, dramatically reducing visible repetition |

> **SNES sprite limits:** 128 sprites total, 32 per scanline — compared to the NES's 64 total and 8 per scanline.  
> Source: [Wikipedia — Super Nintendo Entertainment System: Technical Specifications](https://en.wikipedia.org/wiki/Super_Nintendo_Entertainment_System#Technical_specifications)

---

### Modern Comparison — *Castlevania: Belmont's Curse*

In *Belmont's Curse*, the game screen is constructed as a series of layered 2D rendering passes on a modern GPU:

| Layer | Description |
|---|---|
| **Background parallax layers** | Glowing arched windows, mid-ground stone, foreground platforms scroll at different speeds to simulate spatial depth |
| **Gameplay layer** | Environment collision geometry, interactive objects, and enemies — high-resolution sprite animations with full alpha transparency |
| **Post-processing stack** | Bloom glow, heat distortion, motion blur on whip trails, ambient particle systems (floating embers) |
| **Final composite** | Output at up to 4K with HDR tone mapping — gives the orange fire its intense, almost overexposed luminance |

On the NES, by contrast, the screen was just **two layers**: a background tile layer and a sprite layer, with a hard limit of eight sprites per scanline before flickering. The Game Boy had a similar two-layer architecture at a tiny fixed resolution. Even the SNES, with its four background layers and additive colour math, was fundamentally assembling a flat mosaic of tiles.

*Belmont's Curse* builds its screen the way a **film compositor** would — stacking, blending, and post-processing discrete layers into a unified image. That is architecturally a completely different proposition from anything the retro hardware was capable of.

---

### Tile & Sprite Sizing — Final Comparison

![Final Comparison](https://github.com/user-attachments/assets/b21df205-e760-4462-bdc0-81614220021c)

---

## References

- Carleton University School of Computer Science. *Nintendo Entertainment System NES (Original)* [VIN155]. Vintage Computing Collection. https://carleton.ca/scs/vintage-computing/item/vin155/
- Copetti, Rodrigo. *Game Boy / Color Architecture: A Practical Analysis*. https://www.copetti.org/writings/consoles/game-boy/
- Copetti, Rodrigo. *Super Nintendo / Famicom Architecture: A Practical Analysis*. https://www.copetti.org/writings/consoles/super-nintendo/
- NESdev Wiki. *PPU Palettes*. https://www.nesdev.org/wiki/PPU_palettes
- NESdev Wiki. *PPU Pattern Tables*. https://www.nesdev.org/wiki/PPU_pattern_tables
- NESdev Wiki. *PPU Nametables*. https://www.nesdev.org/wiki/PPU_nametables
- Pan Docs. *OAM – Object Attribute Memory*. https://gbdev.io/pandocs/OAM.html
- Wikipedia. *Super Nintendo Entertainment System — Technical Specifications*. https://en.wikipedia.org/wiki/Super_Nintendo_Entertainment_System#Technical_specifications
