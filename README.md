# Muxcard
## A fully working computer that is *literally* the size of a credit card.

Built around an ESP32-C3, e-paper display and NFC.

The video below shows a little visual demo on just a few things that could be possible.

https://github.com/user-attachments/assets/e4d82f54-b393-4f6b-ad7e-3dc9b4335611

So many things could be possible with this, including:

- Minimalist wallet for QR codes, NFC keys, tickets, boarding passes etc.
- Pentesting & Ethical Hacking similar to Flipper Zero
- Smart-home dashboard & control
- Offline password, 2FA, crypto wallet
- A business card that has a **100% guarantee** to get remembered

<img width="500" height="281" alt="ezgif-6ae57bc187c29872" src="https://github.com/user-attachments/assets/5578b29f-1756-45bf-ab64-3caf5588e36c" />

## 🚀 Follow Development

This project has gotten quite some attention, spreading over the news quite fast, so for all of you who are interested: I plan to launch this project soon, you can sign up to get notified at launch:

E-Mail Sign up: https://muxcard.com
Instagram: instagram.com/muxcard
X: x.com/muxcard

Accounts are fresh and I will try my best to fill them with cool examples asap!

## What Is This?

I’ve always been interested in extreme space constraints — but this one pushed it to another level. Products like AirTag-style card trackers and similar devices that claim to be "credit-card sized" are usually still far away from actually feeling like one.

The idea of a smartcard with display isn't new, there have been multiple concepts and prototypes, but I wanted to build a smartcard that is actually the size of a real credit card - including the actual thickness.

<img width="1280" height="572" alt="CCC_54" src="https://github.com/user-attachments/assets/8788b49f-3b0b-40b8-b04a-2acb28c48387" />

After months of iteration, sleepless nights, frustrating setbacks and a borderline unhealthy obsession over shaving off every single mil of thickness, I can finally hold the very first functioning prototype of a fully working computer the size of an actual credit card.

That tiny difference matters a *lot*.

<img width="898" height="353" alt="CCC-77" src="https://github.com/user-attachments/assets/c40eb855-2c58-42f7-b5ab-9fc634f1b87f" />

To drive this point home: The frame of this is an actual NFC card I have carved out to put in the hardware.

Official ISO7816 smartcards are specified at 0.76mm thickness, but many real-world cards slightly exceed this in practice. The target for this project was simple: Stay around ~1mm total thickness and preserve the illusion of a normal card.

## First & Current Prototype Status

As you can see, this one is a literal 'ugly' prototype, but it serves as a proof of concept to find out what the real challenges are beyond component hieght. Although the first handmade one feels like it would break just by breathing wrong, it gave me good insight into theory in CAD vs real physical stackability because of unplanned things like connections, bending buffer, bonding material, real world tolerances and so on. But in a technicaly perspective, it works very well!

https://github.com/user-attachments/assets/bdd6f6aa-f484-476f-aeac-7d2e1bcbe0bd

I was too impatient for a fab to produce a flexPCB, just to receive it after weeks stuck in customs and finding out it doesn't work because of a stupid mistake, so I went with building my own flexPCB, probably the most DIY method for this kind of thing. I already progressed to professionally manufactured prototypes, but for anyone interested in the process of the custom one: 

<details>
<summary>Here is a deeper dive into the journey of etching my own flexPCB</summary>

PCBs are so dirt cheap these days, but I was so frustrated with all delays and shipping costs that I finally gave in and looked for a way to make my own. After all methods I explored, I actually found out that my 3D printer servers as surprisingly good lithography machine, which is the actual way fabs do it to get to detail no CNC can do.

I needed to somehow export a copper layer to be accepted by my printer. It is possible, but there is a software called UVTools, which is perfect for this and even includes tools specifically for PCB lithography.

For the substrate, I used normal kapton tape with copper foil laminated onto it, covered by a thin photoresist layer. My first attempts let me reconsider my spontaneous motivation of being an independent maker...

<img width="1095" height="680" alt="Screenshot 2026-03-31 at 22 45 27" src="https://github.com/user-attachments/assets/a6582595-1f8e-47ab-8e29-70002c0f2e6f" />

I had to try many different approaches on stackup, chemical concentrations, curing and developing times, but at the end, the details quickly got sharper to the point that it matches the detail you would get for most default professional PCBs.

<img width="892" height="558" alt="Screenshot 2026-04-06 at 21 28 38" src="https://github.com/user-attachments/assets/26868298-ac24-4d94-9933-37b68922f624" />

<img width="910" height="569" alt="Screenshot 2026-04-06 at 21 28 50" src="https://github.com/user-attachments/assets/9473ce25-6937-453a-a12d-5dd53b19479d" />

I was a bit lazy to go the extra mile of figuring out vias and solder mask, so I went with the bare minimum of a single layer and no solder mask, which required some creative workarounds.

Applying solder paste would have been possible by hand, but to my surprise, I was able to make a one use stencil out of pure stacked photoresist film, and it has done a good job:

<img width="3024" height="2164" alt="0248eef6-b6ac-48ab-8942-e94ee54df9ea" src="https://github.com/user-attachments/assets/0248eef6-b6ac-48ab-8942-e94ee54df9ea" />
<img width="580" height="362" alt="dbf97533-f0f8-4c4b-9e7d-8a2e2d2ba1f2" src="https://github.com/user-attachments/assets/dbf97533-f0f8-4c4b-9e7d-8a2e2d2ba1f2" />
<img width="663" height="416" src="https://github.com/user-attachments/assets/5a51594c-b4f7-4488-9400-4c2c92ff227e" />

The thin copper traces also stick surprisingly well to the tape but still need careful handling on fine pitch pads. The biggest downside compared to a normal flexPCB was that too long and thin foil traces ripped appard easily when bending. I was able to solved this by adding more turns on longer nets to avoid strain accumulation.

</details>

This also means that much of the hardware of V0.1 is a 'placeholder'.

- many parts are hand-built and fragile
- I used the rigid version of the display (didn't want to use the flexible ones I have, they're not very available)
- the battery is intentionally undersized for debugging, I consider using 58mAh or 70mAh versions which are potential candidates that fit in.
- assembly currently resembles a tiny crime scene

But the important part is this: *The core concept works.*

No external power.
No hidden electronics outside the card.
No elements that violate the thickness rule.

*Just a ridiculously thin computer.*

> Even though I've spent the last months developing this, the magical moment wasn't the first time it worked, it was the moment I finally removed all the fixtures kapton tape, holding the bare card.

I knew what I was doing, turning this thing to the side and seeing it almost disappearing still amazes me, so it was definitely worth it to go the extra mile to save those seemingly insignificant mils of thickness.

## Current Prototype status

The actual protype is already finished and I will post updates as I'm testing it mostly for durability in daily use and battery life. You can find schematics, layout and some other resources in this repo, but it's still work in progress.

<img width="1089" height="686" alt="Screenshot 2026-05-08 at 17 30 16" src="https://github.com/user-attachments/assets/4ae7b11e-6bba-42bc-8dc7-9ad5e479e9d0" />

I am testing the best and solid ways to implement some features, including:

- a caseless, minimal USB-C port (Main port is magnetic pins)
- micro SD card slot
- different touch button setups
- getting it to tolerate more mechanical stress and bending. It is already good but it's always better to go beyond bare minimum.

## Hardware overview

### MCU: ESP32-C3/S3 or nRF52/53

The current prototype uses an ESP32-C3. It's not the most efficient one on the market, but it is beginner friendly, has good Arduino integration and provides many features including WiFi for occasional API requests. Power consumption is acceptable as the ESP is only active briefly to pull data and/or update the E-Paper. In sleep with RTC on, it consumes around 8uA effectively, which is quite good. I really considered using the nRF52832. Is has a much lower power consumption, sometimes consuming less power on active bluetooth than the ESP32 in idle. It also has a BGA variant which is just 0.4mm thick, perfect for protecting it within the 1mm limit. The ESP32-C3 has a nominal height of 0.85mm. With copper and the other layers, this pushes the limit of 1mm height, meaning almost no protection.

### 1.54" 200*200px E-Paper display

The flexible variant is a must. While it's still not recommended to be bent a lot, it's at least ensuring to avoid immediately cracking on the slightest force applied as it will inevitably deform now and then in a wallet or pocket. It's quite fast and supports partial updates.

<img width="1224" height="644" alt="DSC08642" src="https://github.com/user-attachments/assets/e67c18ac-bfea-41f9-839a-37216057e6ab" />

### IMU: LIS2DW12

Currently working with ST LIS2D. Good feature set, low power. Almost all IMUs are 1mm tall. The BMA530 is just 0.55mm, but its accuracy seems to be sensitive to flexing. The LIS2DW12 is a solid option at 0.7mm. There are also 6-axis IMUs with a gyro, but I'm not sure if it's necessary. An accel seems to be sufficient for the use cases I can think of, especially because it consumes significantly less power, perfect for wake triggers.

### NFC: RC522

Instead of a dynamic tag, I actually want to use a full read/write NFC. The RC522 is common and the current design includes one. There are similar slightly smaller NFC chips which I need to test first. Generally, ISO/IEC 14443 Type A and other common standards are supported, I might find a chip that also supports 125kHz MIFARE.

## Development notes & Engineering challenges

### Robustness & Mechanical stability:

While the thickness limit was a challenge, the bigger one was mechanical stability and material/solder fatigue.

For strain-related issues like trace or solder joint fatigue, simply trying to resist or survive the stress doesn’t help much. Instead, I focused on avoiding strain altogether by creating tactical weak points and placing larger ICs on “islands”, allowing forces to route around sensitive areas so they barely experience meaningful strain in the first place.

This only works if components have enough margin between the upper and lower layers to move slightly instead of being completely fixed. It solves most mechanical issues, but adds a whole new layer of design challenges.

### E-Paper display

Connecting the display turned out to be much harder than expected.

I can’t use normal connectors — even the slimmest ones are barely within the thickness budget and would likely snap under slight bending. Soldering seems like the obvious solution, but the flex connector on this display doesn’t appear to be designed for hot bar soldering. It uses a very fine pitch (0.5mm with 0.2mm gaps), one-sided plating and a thick stiffener that insulates it heavily from heat. So unless I request a custom version, I still need to find a good way to securely connect the display to the main circuit.

For the first prototype, I soldered each wire individually, which was probably in the top 3 most annoying soldering sessions of my life. 

<img width="2350" height="2225" alt="IMG_4006" src="https://github.com/user-attachments/assets/88fc374c-249d-4d6e-8b4e-167eb3487e59" />

It’s a miracle this even worked with all the HV rails almost touching the logic pins. The amount of rework on this part also makes it look veeery ugly...

### Ultra thin LiPo Battery

This is the biggest challenge IMO.

Ultra-thin LiPo batteries exist from around 1mm down to 0.4mm, but reducing thickness comes with a huge capacity penalty that is difficult to balance.

The current prototype uses a 23x23x1mm 30mAh battery, which requires a full cutout in the frame due to reaching the maximum thickness budget. This also means the battery is protected only by the outer layer, with virtually no physical protection.

A smaller battery reduces the attack surface, and if both sides can flex slightly, localised pressure becomes less dangerous as the opposite side can give way. The main remaining risk is compression, since the battery currently has almost no protection against it. Ultra-thin LiPos are usually designed to tolerate a bit more abuse and are naturally less dangerous due to their low capacity, but it’s still something I don’t want to find out on my butt.

My current plan is to switch to a thinner battery (~0.5mm) while using a larger surface area to maintain a useful 30–50mAh capacity. This would allow thin stainless steel layers (similar to PCB stencils) to protect both sides, especially against localized pressure.

Unfortunately, sourcing these batteries is still difficult due to shipping regulations. Even after extensive research, I still couldn’t find a single European or US supplier for these ultra-thin LiPos.

# Current Direction

The focus is turning the concept into something that is not just technically possible, but genuinely practical and robust enough for daily use.

There are still many challenges left to solve including durability, battery life, manufacturability, etc.

But the most important question has already been answered:

> Can a real programmable computer actually exist within credit-card thickness?

YES!

And honestly, even after months of staring at this thing, it still feels slightly absurd every time the display updates while holding what basically feels like a normal card.

# Feedback & Ideas

One of the most interesting parts of this project has been thinking of really cool use cases.

- smart-home dashboard & control?
- offline storage for 2FA, backup keys and passwords?
- pentesting?
- minimalist wallet for membership QR codes, NFC keys, tickets, boarding passes?
- a business card that has a 100% guarantee to get remembered?

Curious what ideas other people come up with.

Feel free to open an issue, share thoughts or suggest interesting use cases. The more ridiculous, the better!
