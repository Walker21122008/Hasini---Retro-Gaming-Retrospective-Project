# Hasini---Retro-Gaming-Retrospective-Project

## Introduction
 
Personally, I am not a huge gamer, unfortunately, and the only game I have played, which was a retro game, was the multiple series of Pac-Man. So, I was thinking about choosing that initially. During my research through all the possible games, I came across Castlevania and fell in love with the series since it felt like the inverse of my favourite movie series, Hotel Transylvania.
 
What I didn't expect was how much the visuals would differ across the three versions. That ended up becoming the focus of this retrospective, which is what the game looks like and why it looks so different on each platform. The NES, Game Boy, and SNES each have hard limits on how many colours they can display, how many sprites they can draw per scanline, and how much video memory they have to work with. They show up directly in what appears on screen, and Castlevania makes those differences very visible because the same castle, the same enemies, and the same character have to be drawn within completely different constraints on each system.

Three main things I am going to focus on: 
- **Color Palettes**  
  How each platform handles color limitations (NES’s restricted palette, Game Boy’s grayscale tones, SNES’s expanded color range) and how that affects mood and detail.

- **Tile & Sprite Sizing**  
  Differences in tile sizes and sprite dimensions used to build characters and environments, and how this impacts character detail and animation.

- **Sprite Rendering Constraints**  
  Limits on how many sprites can appear per scanline and overall memory usage, influencing flickering, layering, and on-screen complexity.

The three games I traced:
 
- **Castlevania** (NES, 1987) - the original. Simon Belmont, a whip, a castle, and Dracula.
- **Castlevania: The Adventure** (Game Boy, 1989) - the first portable entry, released the same year as the Game Boy itself.
- **Super Castlevania IV** (SNES, 1991) - the 16-bit reimagining. Widely considered one of the best games on the system.

---
 
## 1. Colour Palettes
 
*How each platform handles colour limitations and how that affects mood and visual detail.*
 
---

<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (3)" src="https://github.com/user-attachments/assets/f450bce7-5d5a-4ecc-8df9-230bce3f7b83" />
Here you can see the title screen in all the three devices.
 
### NES (Castlevania)
<img width="270" height="368" alt="image" src="https://github.com/user-attachments/assets/6c972394-1151-4f8c-8a0f-68e50ad56951" />

**Hardware:** The Ricoh 2C02 PPU outputs at 256×240 pixels with a fixed master palette of 54 colours, of which only 25 can appear on screen simultaneously. Backgrounds get 13 colour slots (four sub-palettes of 3 colours each plus one shared background colour) and sprites get 12 (four sub-palettes of 3 plus transparency). [[Carleton University SCS Vintage Computing Collection — VIN155](https://carleton.ca/scs/vintage-computing/item/vin155/)]
 
**What I played:** `Castlevania (USA).nes` — loaded into FCEUX, launched from the terminal with `fceux`. Died repeatedly in Stage 1 and barely saw Stage 2.

 <img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (4)" src="https://github.com/user-attachments/assets/ae917bfa-c88d-4016-9f35-e4dce0b93879" />

I saw that the Castlevania title screen uses only 10 colors because it is rendered entirely as a single background layer, which is hardware-limited to a maximum of 13 colors (four 3-color palettes plus one shared background color). The theoretical maximum of 25 colors on the NES is only achievable when 12 additional colors are provided by moving sprites; however, since this title screen contains no active sprite objects, that entire half of the system's color capacity remains inaccessible. Technical documentation of the NES Picture Processing Unit (PPU) confirms this "background vs. sprite" split, and ROM analysis shows the artists further limited themselves to 10 colors to avoid visual "clashing" at the borders of the mandatory 16x16 pixel attribute grid. [NES Dev Wiki]

When I was playing the game, I was pretty astonished about how the artists where able to reuse the setting screen with the color limitations to make the game pretty fun to play. The setting’s palette leverages the NES’s background limitations to create a somber, gothic atmosphere, using deep blues and blacks to represent a moonlit night while saving vibrant greens and oranges for foreground foliage and structures. Because the background is restricted to four 3-color palettes, I was curious what the artists used to make the castle gradients. Here, after a bit of research, the artists used dithering (checkerboard pixel patterns) to simulate gradients and textures on the castle walls. 
 
<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (5)" src="https://github.com/user-attachments/assets/d4c0e132-a49a-40ad-98eb-ed27cdbeb3cc" />

Simon Belmont's sprite design is a masterclass in efficiency, utilizing just three colors—tan, brown, and red—plus a transparency channel to fit the NES's strict palette rules (All spries must have only three colors). To bypass these limits, artists used a technique called "open outlining," where the black background of the castle "bleeds" into his silhouette to act as a faked fourth color for his hair and boots. Simon Belmont's vibrant red tunic provides high contrast against the cool, dark blues of the environment to ensure he remains the focal point. Furthermore, to prevent the whip from exceeding the three-colour limit, the game renders it as a separate sprite using its own dedicated palette, allowing the weapon to appear in different shades (like light purple and white) without interfering with Simon’s primary character colors.
<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (6)" src="https://github.com/user-attachments/assets/278fc135-4002-45c0-8f5b-d49a614b019b" />

---
 
### Game Boy (Castlevania: The Adventure)
<img width="314" height="317" alt="image" src="https://github.com/user-attachments/assets/be3cc3e3-2c1e-44fd-b3a6-ca05dc2f7f12" />

 
**Hardware:** The Game Boy display outputs at 160×144 pixels with exactly 4 shades of gray — no colour at all. On the original hardware, those shades appear on a green-tinted LCD, so the image looks slightly olive rather than true black and white. Every 8×8 pixel tile is limited to these four shades, and one shade in every sprite palette must be reserved for transparency so sprites don't appear as solid blocks. [[Copetti, *Game Boy / Color Architecture*](https://www.copetti.org/writings/consoles/game-boy/)]
 
**What I played:** `Castlevania - The Adventure (USA).gb` — loaded into mGBA (`mgba-qt`). Found it easier to survive than the NES version, but it felt stripped down.
 

The Game Boy title screen for Castlevania: The Adventure operates under a strict four-shade monochrome palette, forcing Konami to abandon the NES’s color variety in favor of extreme pixel-level detail. To compensate for the lack of hue, artists employed advanced dithering—fine checkerboard and stippling patterns—to simulate textured stone and complex shading within the logo, giving it a grittier, more weathered appearance than its NES predecessor. By sacrificing side-scenery to focus memory on high-resolution typography, the design achieves a "premium" gothic look through sharp contrast, using the darkest black against the lightest white to ensure every jagged edge remains legible on the small, non-backlit handheld screen.
<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (7)" src="https://github.com/user-attachments/assets/9fd831ff-73a6-400f-8940-14c779118cd8" />

In this gameplay shot of Castlevania: The Adventure, the four-shade monochrome palette is pushed to its limit to create depth in a color-free environment. Konami used a "layered" shading strategy: the furthest background (the sky) is the lightest shade, the mid-ground trees use mid-tones with heavy vertical dithering to simulate bark texture, and the immediate foreground—including Christopher Belmont and the enemies—uses the darkest blacks to ensure they remain distinct. Unlike the NES, which used distinct hues to separate objects, the Game Boy relies on repeated color schemes across all elements, forcing sprites and background tiles to share the same four shades of grey. This lack of color variety results in a "bland," flat appearance where detail is achieved through texture rather than tone. While the NES could use high-contrast reds and blues to make Simon pop, the Game Boy's restricted palette often causes the hero and enemies to blend into the environment, a stark contrast to the clear, vibrant layering possible on home consoles.
<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (8)" src="https://github.com/user-attachments/assets/a8bb6eb9-e3ee-40e3-bcea-7728970fedca" />

While Christopher Belmont’s sprite in The Adventure looks "bland" by modern standards, its design was a calculated response to the Game Boy's motion blur and low contrast. To prevent the character from becoming an unreadable smudge due to the screen’s slow refresh rate, Konami utilized "safety simplicity," avoiding fine internal lines in favor of solid blocks of light grey and thick, dark-black outlines that maintain a clear silhouette. This required a "palette flattening" strategy, where artists bypassed the muddy middle-grey shades to use only the extremes, resulting in a flat, paper-cutout appearance. Consequently, the character seems to merge into the background, as both the hero and the environment must share the same limited four-shade palette. Because there are no distinct colors to separate the layers, the sprite often becomes visually entangled with similarly shaded mid-ground elements like the dithered trees, forcing the player to rely on the thick black outline as the only consistent anchor against the environmental detail.
<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (9)" src="https://github.com/user-attachments/assets/91500965-01b3-49e7-99ba-202bb723dc68" />

---
 
### SNES
 
**Hardware:** The SNES can display 256 colours simultaneously from a master palette of 32,768. Two dedicated PPU chips handle all graphics output, enabling colour blending, gradients, and transparency effects that neither the NES nor Game Boy could produce. [[Copetti, *Super Nintendo / Famicom Architecture*](https://www.copetti.org/writings/consoles/super-nintendo/)]
 
**What I played:** `Super Castlevania IV` — loaded into Snes9x. Made it through the first several stages.
 
With a massive jump to 256 simultaneous colors out of a master palette of 32,768, Super Castlevania IV completely removes the color restrictions that defined the earlier series entries. This expanded range allows the title screen to feature complex gradients and subtle shading on the stone wall—using dozens of variations of purple, grey, and green—that were impossible on the NES, which was limited to just 13 background colors. While the Game Boy relied on a flat, four-shade monochrome palette and the NES used high-contrast "blocks" of color to define depth, the SNES uses its dual Picture Processing Units to enable smooth transparency and lighting effects. The result is a richly detailed, atmospheric scene where the vines and metallic logo feel tactile and three-dimensional, a stark evolution from the gritty dithering of the handheld version and the simplified primary colors of the 8-bit era  

<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (10)" src="https://github.com/user-attachments/assets/f837e242-a9a7-4e7c-9715-40d9dda05aee" />

Super Castlevania IV utilizes the SNES's dual Picture Processing Units (PPUs) to revolutionize gothic environmental storytelling through advanced color depth and math. Unlike the 8-bit era's flat fills, the background uses a sub-palette mixing technique to create a seamless deep purple-to-black gradient, simulating a vast, moonlit sky without the "staircase" banding typical of the NES's attribute limits. By leveraging the 16-color-per-tile capacity, artists applied high-density color indexing to rock formations and the mossy "skull," layering dozens of grey and green values within a single 8x8 block to create organic textures like weathered stone and decaying flora. Most impressively, the game employs hardware-level alpha blending on the hanging vines and distant skull, mathematically calculating the average value between overlapping layers to produce a translucent "fog" effect.
<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (11)" src="https://github.com/user-attachments/assets/b8c32744-31c2-4721-a71b-2e9f15ccb3c1" />

The SNES design of Simon Belmont represents a massive leap in pixel anatomy, moving from the NES's three-color "metasprite" to a rich 16-color palette that enables realistic material physics. This expanded range allows for color ramping to simulate the glint of moonlight on metallic armor and leather through specular highlights—a technique impossible under the "palette poverty" of the 8-bit era. Unlike the "palette flattening" and thick safety outlines required on the Game Boy to combat motion blur, the SNES sprite uses subtle anti-aliased shading and warm-to-cool hue contrast to pop against the purple backgrounds. Furthermore, the whip is no longer a solid-colored overlay but a complex, multi-jointed object with its own color depth, allowing for fluid motion and metallic textures that would have caused massive hardware flickering on previous systems.
<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (12)" src="https://github.com/user-attachments/assets/29eb7743-e51f-47ad-bc98-2f46cc289d8e" />

| Category | 🎮 NES | 🟢 Game Boy | 🟣 SNES |
|---|---|---|---|
| **Title Screen - Colour Count** | 10 colours (background layer only; no active sprites to access the 12 sprite-palette slots) | 4 shades of grey (monochrome only) | Hundreds of colour variations from the 256-simultaneous palette |
| **Title Screen - Key Technique** | Artists self-limited to 10 colours to avoid visual clashing at the mandatory 16×16 attribute grid borders | Advanced dithering (checkerboard + stippling) simulates stone texture and logo shading without hue | Smooth gradients, hardware alpha blending, and translucent fog effects impossible on earlier hardware |
| **Gameplay Screen = Key Limitation** | Hard colour boundaries at every 16×16 attribute block | All elements share the same four greys — sprites frequently blend into mid-ground tiles of matching tone | None meaningful; hardware alpha blending produces translucent vine-and-fog layers |
| **Gameplay Screen - Mood** | Clear, readable depth; each layer identifiable at a glance | Texture-heavy but flat; depth comes from outline weight, not colour | Volumetric and atmospheric; the environment feels three-dimensional for the first time in the series |
| **Main Character - Colours Used** | 3 colours (tan, brown, red) + transparency | 2 effective shades (light grey + black), avoiding muddy middle greys ("palette flattening") | Full 16-colour palette with colour ramping for specular highlights |
| **Main Character - Weapon** | Whip rendered as a *separate sprite* on its own palette (light purple + white) to avoid exceeding the 3-colour limit | Whip simplified to match the same constrained palette as the character | Whip is a multi-jointed object with its own colour depth, enabling fluid motion and metallic texture without hardware flickering |

---
 
## 2. Tile and Sprite Sizing
 
*Differences in tile sizes and sprite dimensions used to build characters and environments*
 
---

### NES (Castlevania)


**Hardware:** The NES Picture Processing Unit, the Ricoh 2C02, renders everything from one fundamental unit: the 8×8 pixel tile which is every background, wall, and floor is assembled from these fixed blocks, stored in memory as Pattern Tables (CHR).
- Each tile costs 16 bytes across two bitplanes, giving each pixel one of four values that index into a colour sub-palette [NESDev Wiki — PPU Pattern Tables]
- Backgrounds are laid out on a 32×30 nametable (960 tiles mapping exactly to the 256×240 screen), but colour is assigned per 2×2 tile group via the Attribute Table meaning colour boundaries are locked to 16-pixel intervals and two adjacent tiles sharing an attribute cell cannot be coloured independently [NESDev Wiki — PPU Nametables]

## References
 
- Carleton University School of Computer Science. *Nintendo Entertainment System NES (Original)* [VIN155]. Vintage Computing Collection. https://carleton.ca/scs/vintage-computing/item/vin155/
- Copetti, Rodrigo. *Game Boy / Color Architecture: A Practical Analysis*. https://www.copetti.org/writings/consoles/game-boy/
- Copetti, Rodrigo. *Super Nintendo / Famicom Architecture: A Practical Analysis*. https://www.copetti.org/writings/consoles/super-nintendo/
- NESdev Wiki. PPU Palettes. https://www.nesdev.org/wiki/PPU_palettes

 
