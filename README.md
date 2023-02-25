# Pioneer-CdPi1000NexusX
Cdj1000mk3 midi hack with mixxx stand-alone in rpi4
Hello fellow programmers and Dj’s alike,
I would like to present the project I have been working on for the last few weeks.

To put it in context, I've been a Dj for about 15 years and my current setup is 4x Pioneer CDJ400 + Pioneer DJM800 using MIDI HID with TraktorPro3, which is a good setup but I'm looking for something even more club friendly, more standardized equipment and music preparing using RekordBox.
I want basically the same setup at home that I use when I go playing at a club.

Then I found the “Anatsko Andrei aka djgreeb” project!!!! (https://github.com/djgreeb/CDJ-1000mk3_new_life_project)

A great “Thank You” to Andrei due to his wonderful work on retro-engineering the SPI communication on CDJ between the LCD and the main board.

And I found my new objective:
Playing at home with 4x Cdj1000mk3 Nexus2 style + DJM800, crazy setup I think….


It turns out that after some analysis of the original project from “Andrei” I came to the conclusion that there were some functions I would need, and since I don't know how to program in ‘C++’ I found another way to mimic the CDJ2000NSX2's GUI without using his project (cdj2000v1) but having it as a inspiration.
The board used by him was a “STM32F746 - DISCOVERY”, and it had limited resources and it is more expensive than Rpi4 board so I decided to use my old Rpi4 from my Home Assistant server for R&D for my new device since it has a lot more processing power and more upgradability, boot from SSD/NVME, etc 

From now my project will be called: 

!!!!!   Pioneer CdPi1000NexusX !!!!!



I’m just starting to learn how to program .XML and .QSS so it's a slow development at least for now.

My goal is to use Cdj1000Mk3 via MIDI (STM32F429I makes the conversion of SPI into MIDI) to Rpi4 with MIXXX installed, with the new skin I'm designing.

I will share in the next few days the LCD panel to be 3D printed, the buttons on the display panel and maybe some buttons that exist on cdj2000nsx2 and not on cdj1000. (quantize, slip mode, loop cutter, etc)
Still analyzing physical differences from 1000 to 2000nsx2 to choose the best way to put the missing buttons into the CDJ1000 case.

Will implement the missing buttons on the hardware and will be using an extra Arduino Teensy to create a MIDI controller just for the additional buttons, pots, and LEd’s that are missing from 1000 to 2000Nsx2 and also the Display buttons and encoders. 
So my device will have 2 MIDI lines, one coming from Teensy and another from STM32 and will join them at RPI4.


But since “Andrei” mimicked the Cdj2000v1 why not try myself to mimic the Cdj2000NSX2 with a bigger screen.

The OEM screen specs of NSX2 are 7.1” screen size with 1280*768 of resolution. I can find a similar spec screen for Rpi4 for 40-50€ / 40-50$


I’m using QT Designer to create the widgets using a downloaded picture of the screen as a template to retro-engineer the OEM Pioneer GUI since I think that is the best way of generating a ‘.QSS’ and ‘.XML’ for newbies.
However if someone is proficient in “Nokia QT designer” or skinning on MIXXX I would happily pay for some co-designing and co-development of this project.


Goals:

✅ Cdj1000mk3 MIDI hack - DONE (credits to: Anatsko Andrei aka djgreeb and Vandoeselaar) 
https://github.com/freddykat/CDJ-1000-mk3-for-Rekordbox

✔️❌MIXXX skin that match to original pioneer GUI (under development)
(I must give credit to “timewasternl” because I inspire myself with his skin and I'm currently adapting his skin to my needs)
	https://github.com/timewasternl/Pioneered


❌ Rekordbox OEM MIDI integration (still missing the PID/VID from a CDJ2000NSX2 to be identified)

❌ MIDI clock sharing via network to other players

❌ PRE-COMPILED MIXXX PI IMAGE + Pioneer CdPi2000NexusX Skin

All the necessary files will be available on my github for anyone who needs them, but the goal is to have a .IMG to be burned into a SD using Balena-Etcher and be really a Plug & Play system apart from the 5 SPI wires from the CDJ mainboard to the STM32F429I board and USB from STM32F429I to RPI.

