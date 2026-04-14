# Hasini---Retro-Gaming-Retrospective-Project

## Introduction
 
I picked the Castlevania franchise because I'd heard of it when I was younger
 
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
 
### NES
 
**Hardware:** The Ricoh 2C02 PPU outputs at 256×240 pixels with a fixed master palette of 54 colours, of which only 25 can appear on screen simultaneously. Backgrounds get 13 colour slots (four sub-palettes of 3 colours each plus one shared background colour) and sprites get 12 (four sub-palettes of 3 plus transparency). [[Carleton University SCS Vintage Computing Collection — VIN155](https://carleton.ca/scs/vintage-computing/item/vin155/)]
 
**What I played:** `Castlevania (USA).nes` — loaded into FCEUX, launched from the terminal with `fceux`. Died repeatedly in Stage 1 and barely saw Stage 2.

 <img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (4)" src="https://github.com/user-attachments/assets/ae917bfa-c88d-4016-9f35-e4dce0b93879" />

The Castlevania title screen uses only 10 colors because it is rendered entirely as a single background layer, which is hardware-limited to a maximum of 13 colors (four 3-color palettes plus one shared background color). The theoretical maximum of 25 colors on the NES is only achievable when 12 additional colors are provided by moving sprites; however, since this title screen contains no active sprite objects, that entire half of the system's color capacity remains inaccessible. Technical documentation of the NES Picture Processing Unit (PPU) confirms this "background vs. sprite" split, and ROM analysis shows the artists further limited themselves to 10 colors to avoid visual "clashing" at the borders of the mandatory 16x16 pixel attribute grid. [NES Dev Wiki]

The setting’s palette leverages the NES’s background limitations to create a somber, gothic atmosphere, using deep blues and blacks to represent a moonlit night while saving vibrant greens and oranges for foreground foliage and structures. Because the background is restricted to four 3-color palettes, the artists used dithering (checkerboard pixel patterns) to simulate gradients and textures on the castle walls. 
 
<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (5)" src="https://github.com/user-attachments/assets/d4c0e132-a49a-40ad-98eb-ed27cdbeb3cc" />

Simon Belmont's sprite design is a masterclass in efficiency, utilizing just three colors—tan, brown, and red—plus a transparency channel to fit the NES's strict palette rules (All spries must have only three colors). To bypass these limits, artists used a technique called "open outlining," where the black background of the castle "bleeds" into his silhouette to act as a faked fourth color for his hair and boots. Structurally, Simon is a metasprite built from multiple 8x8 tiles, his vibrant red tunic provides high contrast against the cool, dark blues of the environment to ensure he remains the focal point. Furthermore, to prevent the whip from exceeding the three-colour limit, the game renders it as a separate sprite using its own dedicated palette, allowing the weapon to appear in different shades (like light purple and white) without interfering with Simon’s primary character colors.
<img width="1280" height="720" alt="Simon Belmont takes up approximately 10 tiles  (6)" src="https://github.com/user-attachments/assets/278fc135-4002-45c0-8f5b-d49a614b019b" />

---
 
### Game Boy
 
**Hardware:** The Game Boy display outputs at 160×144 pixels with exactly 4 shades of gray — no colour at all. On the original hardware, those shades appear on a green-tinted LCD, so the image looks slightly olive rather than true black and white. Every 8×8 pixel tile is limited to these four shades, and one shade in every sprite palette must be reserved for transparency so sprites don't appear as solid blocks. [[Copetti, *Game Boy / Color Architecture*](https://www.copetti.org/writings/consoles/game-boy/)]
 
**What I played:** `Castlevania - The Adventure (USA).gb` — loaded into mGBA (`mgba-qt`). Found it easier to survive than the NES version, but it felt stripped down.
 
soon to be

The title screen is the clearest colour comparison between platforms. The NES title uses a black background with a green logo and red banner — colour contrast doing the work of separating elements. Here there is no colour contrast. Everything is communicated through shade alone. Konami chose a white background with a black logo because those are the two most distinct shades available; there is no option for a coloured logo or a coloured banner. The gothic lettering uses thick outlines for the same reason — on a four-shade display, outlines are the only reliable way to make a foreground element read against a background that might be a similar shade.
 
soon to be

In gameplay the lack of colour creates genuine readability problems. The skeleton enemy in the center of this screenshot blends into the background columns and mountain silhouette — they're all rendered in similar shades of gray. On the NES, colour contrast separates enemies from backgrounds automatically: orange bricks read as floor, gray stone as wall, pink enemies as threats. The Game Boy has no such shortcut. Distinguishing platforms from hazards from enemies requires more active attention here than it ever did on the NES.
 
---
 
### SNES
 
**Hardware:** The SNES can display 256 colours simultaneously from a master palette of 32,768. Two dedicated PPU chips handle all graphics output, enabling colour blending, gradients, and transparency effects that neither the NES nor Game Boy could produce. [[Copetti, *Super Nintendo / Famicom Architecture*](https://www.copetti.org/writings/consoles/super-nintendo/)]
 
**What I played:** `Super Castlevania IV` — loaded into Snes9x. Made it through the first several stages.
 
soon to be

The SNES title screen uses colour in ways the NES and Game Boy simply cannot. The logo has shading and depth — multiple tones blending across the same letterform. The background is not flat black like the NES version; it has tonal variation. The candles animate with smooth gradients. This is what 256 simultaneous colours from a palette of 32,768 looks like compared to 25 from 54, or four shades of gray. The mood is darker and more atmospheric because the palette can actually render shadow and depth, not just flat blocks of colour.
 
soon to be 

In gameplay the expanded palette means environments have texture and mood rather than flat colour blocks. The stonework has highlight and shadow built into the tiles themselves. The background layers use slightly different colour values to create depth — something the NES's single background layer and 25-colour limit couldn't support. The visual complexity here isn't just about having more colours; it's about being able to use gradients and shading to imply three-dimensionality in a 2D game.
 

## Platform 2: Game Boy (Sharp LR35902, 4.19 MHz, 8-bit)
 
### Game Played: Castlevania: The Adventure
<img width="314" height="317" alt="image" src="https://github.com/user-attachments/assets/be3cc3e3-2c1e-44fd-b3a6-ca05dc2f7f12" />
 
#### Hardware Context
The Game Boy is built around a single-chip design Nintendo called the **DMG-CPU**, manufactured by Sharp. Inside it is a **Sharp SM83** processor, a hybrid of the Zilog Z80 and Intel 8080 running at **4.19 MHz**. As Rodrigo Copetti's architectural analysis notes, clock speed alone can be deceiving here: the SM83's design means it doesn't always complete instructions as quickly as the raw MHz might suggest. [[Copetti, *Game Boy / Color Architecture*](https://www.copetti.org/writings/consoles/game-boy/)]
 
The Game Boy has **8 KB of RAM**, which is four times what the NES had, but its graphics pipeline is more limited in other ways. The display runs at **160×144 pixels** with only **4 shades of gray**, and due to the green-tinted LCD on the original hardware, the image appears slightly greenish rather than true black and white. All graphics calculations are handled by the CPU, then passed to a dedicated PPU for rendering. Audio has four channels: two pulse waves, a wave channel, and a noise channel, one fewer than the NES, and with no DPCM sample channel at all.

#### What I Played
`Castlevania - The Adventure(USA).gb` - This is the first Castlevania on a handheld. I played through all four stages. I also briefly tried Castlevania II: Belmont's Revenge (1991) for comparison - it is notably better, and that comparison ended up being useful.

#### Observations
The title screen looks noticeably flatter than the NES version, even though the Game Boy came out two years later. That's because the Game Boy's display outputs only four shades of gray on a 160×144 screen compared to the NES's 25 simultaneous colours on a 256×240 display. The NES title screen uses colour contrast to separate the foreground logo from the background. Here, everything has to be communicated through shade alone, and on the original olive-green LCD, even those four shades bleed into each other.
![gameboyCastlevaniaTitlescreen](https://github.com/user-attachments/assets/6fdfe9f5-948d-4d00-a096-a0dc573ed51d)

This game was super monotone and constricted according to my opinion compared to the NES version. The main character, Christopher Belmont moves slower than Simon Belmont on the NES noticeably, measurably slower even though the Game Boy's CPU runs at 4.19 MHz compared to the NES's 1.79 MHz. The higher clock speed doesn't mean much here because the Game Boy had no dedicated PPU like the NES's Ricoh 2C02. All the rendering work fell back on the main CPU, and in scenes with multiple enemies, the frame rate visibly drops. The character speed was likely tuned down to match what the hardware could sustain. The sub-weapons from the NES which are the crucifix, holy water, bows are gone entirely. The NES managed multiple projectiles onscreen using sprite flickering, but on this small monochrome display that flickering would have been even more distracting than on a colour TV. Removing them was the best call, but it also makes the game feel stripped down compared to what came before.
![gameboyCastlevanieGameplayScreen](https://github.com/user-attachments/assets/c6449a4d-2adf-46c3-99be-1a676de0bc89)


## Platform 3: SNES (Ricoh 5A22, 3.58 MHz, 16-bit)

### Game Played: Super Castlevania IV
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/d1561301-862a-45df-ab20-c723cf133dac" />

 
#### Hardware Context
The SNES is built around the **Ricoh 5A22**, a customised version of the WDC 65C816 — a 16-bit extension of the same 6502 family the NES used. As Rodrigo Copetti's architectural analysis notes, the CPU runs at a **variable clock speed**, reaching up to **3.58 MHz** for register operations but dropping to **1.79 MHz** when accessing slower buses. That ceiling of 3.58 MHz is only marginally faster than the NES's 1.79 MHz, and Copetti points out the 65C816's design is "excessively cumbersome for little gain" compared to competing chips of the era. [[Copetti, *Super Nintendo / Famicom Architecture*](https://www.copetti.org/writings/consoles/super-nintendo/)]
 
Ricoh added dedicated **multiplication and division units** directly to the 5A22, since the base 65C816 lacked these instructions entirely. Two **DMA (Direct Memory Access) units** allow data to move around memory without interrupting the CPU. Two dedicated **PPU chips** handle all graphics, enabling hardware-level scaling, rotation, and multiple background layer modes — Mode 7 being the most famous. A separate **Sony SPC700 audio chip** runs its own processor with 64 KB of dedicated RAM, handling 8-channel stereo sound with full sample playback. The colour palette allows 32,768 possible colours with 256 displayable simultaneously compared to the NES's 54-colour master palette and 25 on screen at once, and the Game Boy's 4 shades of gray.

#### What I Played

#### Observations

## References
 
- Carleton University School of Computer Science. *Nintendo Entertainment System NES (Original)* [VIN155]. Vintage Computing Collection. https://carleton.ca/scs/vintage-computing/item/vin155/
- Copetti, Rodrigo. *Game Boy / Color Architecture: A Practical Analysis*. https://www.copetti.org/writings/consoles/game-boy/
- Copetti, Rodrigo. *Super Nintendo / Famicom Architecture: A Practical Analysis*. https://www.copetti.org/writings/consoles/super-nintendo/
- NESdev Wiki. PPU Palettes. https://www.nesdev.org/wiki/PPU_palettes

 
