# Hasini---Retro-Gaming-Retrospective-Project

## Introduction
 
I picked the Castlevania franchise because I'd heard of it when I was younger
 
What I didn't expect was how much the visuals would differ across the three versions. That ended up becoming the focus of this retrospective, which is what the game looks like and why it looks so different on each platform. The NES, Game Boy, and SNES each have hard limits on how many colours they can display, how many sprites they can draw per scanline, and how much video memory they have to work with. They show up directly in what appears on screen, and Castlevania makes those differences very visible because the same castle, the same enemies, and the same character have to be drawn within completely different constraints on each system.

The three games I traced:
 
- **Castlevania** (NES, 1987) - the original. Simon Belmont, a whip, a castle, and Dracula.
- **Castlevania: The Adventure** (Game Boy, 1989) - the first portable entry, released the same year as the Game Boy itself.
- **Super Castlevania IV** (SNES, 1991) - the 16-bit reimagining. Widely considered one of the best games on the system.

## Platform 1: NES (Ricoh 2A03, 1.79 MHz, 8-bit)

### Game Played: Castlevania
<img width="270" height="368" alt="image" src="https://github.com/user-attachments/assets/36858aee-9cda-44b3-9c09-302f77841510" />
 
#### Hardware Context
The NES was built around a Ricoh 2A03, which is a custom chip derived from the MOS 6502, running at 1.79 MHz. It had 2 KB of RAM and 2 KB of dedicated video RAM. For graphics, a dedicated Ricoh 2C02 PPU (Picture Processing Unit) handled sprites and backgrounds separately, outputting at 256×240 pixels, but was limited to 25 on-screen colours at a time from a palette of 54, with a maximum of 64 total sprites and only 8 per scanline. Audio was handled by five channels built directly into the 2A03: two pulse waves, a triangle wave, a noise channel, and a DPCM channel for short sampled sounds. [[Carleton University SCS Vintage Computing Collection — VIN155](https://carleton.ca/scs/vintage-computing/item/vin155/)]

The NES used strict cartridge-based hardware licensing and a lockout chip (the 10NES) to control what software could run on the platform. There was no general-purpose operating system; the hardware itself handled graphics, sound, and input directly, meaning every cycle of that 1.79 MHz CPU was available to the game. No dedicated co-processor for math, no hardware scaling, no rotation. Everything had to be done in software.
<img width="500" height="500" alt="NES-Console-Set" src="https://github.com/user-attachments/assets/f2103e25-66cf-4e90-9b43-7ebdbedd4297" />

#### What I Played
`Castlevania (USA).nes` - loaded into FCEUX, launched from the Linux terminal with `fceux`. I am genuinely bad at video games, and Castlevania made sure I knew it. I died repeatedly in Stage 1 before I got far enough to see Stage 2. Most of my time with this game was spent replaying stage 1 again and again.

#### Observations
The background is pure black. The NES can only show 25 colours at once, so Konami spent those slots on the logo and left the background empty. You can count the colours used: green logo, red banner, purple outline, orange castle, gray borders. That's most of the palette already gone on just the title screen. When I counted it, I found that about 13 colours were used from the colour palette, so Konami did not use the remaining 12 colours.
![0](https://github.com/user-attachments/assets/f55e4a7c-020f-424f-a255-7f2a63ed5af2)

This is Stage 1 aka the room where I spent most of my lives. The two pink blob enemies and the background share a limited colour palette, and you can see the tile repetition clearly: the same stone wall tile is reused across the entire background, the same candle sconce appears twice in the same frame. The NES only has 2 KB of video RAM, so backgrounds are built from a small set of repeated 8×8 tiles (Since my screenshot is a bit stretched out, I will show an estimate of how the screen is broken down into tiles). The SNES has dedicated VRAM for its two PPU chips and can hold far more unique tile data, which is why its environments look varied rather than patterned. I found this 8x8 tile patternrn by breaking down the floor tiles and then breaking down the candles and wall accordingly, as shown in the image below.
<img width="1280" height="720" alt="Untitled design (11)" src="https://github.com/user-attachments/assets/edb827fc-b82c-4455-9b40-299335f8375a" />

I did make it to Stage 2. The blue bat-like enemies at the top of this screen are a good example of the NES sprite system in action. Each one is a small sprite with a two-colour palette, moving in arcs that the CPU has to calculate in software. There is no co-processor handling this; the Ricoh 2A03 at 1.79 MHz is doing all the enemy actions, which are collision detection and movement math simultaneously. The staircase geometry here is entirely built from the same tile set as Stage 1, just rearranged, not redrawn. That's the 2 KB VRAM budget at work again. 
![castlevaniagameplaypart2](https://github.com/user-attachments/assets/cc6fdc03-74b9-46bd-94e5-268b86a5ed48)



## Platform 2: Game Boy (Sharp LR35902, 4.19 MHz, 8-bit)
 
### Game Played: Castlevania: The Adventure
<img width="314" height="317" alt="image" src="https://github.com/user-attachments/assets/be3cc3e3-2c1e-44fd-b3a6-ca05dc2f7f12" />
 
#### Hardware Context
The Game Boy is built around a single-chip design Nintendo called the **DMG-CPU**, manufactured by Sharp. Inside it is a **Sharp SM83** processor, a hybrid of the Zilog Z80 and Intel 8080 running at **4.19 MHz**. As Rodrigo Copetti's architectural analysis notes, clock speed alone can be deceiving here: the SM83's design means it doesn't always complete instructions as quickly as the raw MHz might suggest. [[Copetti, *Game Boy / Color Architecture*](https://www.copetti.org/writings/consoles/game-boy/)]
 
The Game Boy has **8 KB of RAM**, which is four times what the NES had, but its graphics pipeline is more limited in other ways. The display runs at **160×144 pixels** with only **4 shades of gray**, and due to the green-tinted LCD on the original hardware, the image appears slightly greenish rather than true black and white. All graphics calculations are handled by the CPU, then passed to a dedicated PPU for rendering. Audio has four channels: two pulse waves, a wave channel, and a noise channel, one fewer than the NES, and with no DPCM sample channel at all.

#### What I Played
Castlevania: The Adventure (1989). This is the first Castlevania on a handheld. I played through all four stages. I also briefly tried Castlevania II: Belmont's Revenge (1991) for comparison - it is notably better, and that comparison ended up being useful.

#### Observations
The title screen looks noticeably flatter than the NES version, even though the Game Boy came out two years later. That's because the Game Boy's display outputs only four shades of gray on a 160×144 screen compared to the NES's 25 simultaneous colours on a 256×240 display. The NES title screen uses colour contrast to separate the foreground logo from the background. Here, everything has to be communicated through shade alone, and on the original olive-green LCD, even those four shades bleed into each other.

This game was super monotone and constricted according to my opinion compared to the NES version. The main character, Christopher Belmont moves slower than Simon Belmont on the NES noticeably, measurably slower even though the Game Boy's CPU runs at 4.19 MHz compared to the NES's 1.79 MHz. The higher clock speed doesn't mean much here because the Game Boy had no dedicated PPU like the NES's Ricoh 2C02. All the rendering work fell back on the main CPU, and in scenes with multiple enemies, the frame rate visibly drops. The character speed was likely tuned down to match what the hardware could sustain. The sub-weapons from the NES which are the crucifix, holy water, bows are gone entirely. The NES managed multiple projectiles onscreen using sprite flickering, but on this small monochrome display that flickering would have been even more distracting than on a colour TV. Removing them was the best call, but it also makes the game feel stripped down compared to what came before.

## Platform 3: SNES (Ricoh 5A22, 3.58 MHz, 16-bit)

### Game Played: Super Castlevania IV
 
#### Hardware Context

#### What I Played

#### Observations

## References
 
- Carleton University School of Computer Science. *Nintendo Entertainment System NES (Original)* [VIN155]. Vintage Computing Collection. https://carleton.ca/scs/vintage-computing/item/vin155/
- Copetti, Rodrigo. *Game Boy / Color Architecture: A Practical Analysis*. https://www.copetti.org/writings/consoles/game-boy/
