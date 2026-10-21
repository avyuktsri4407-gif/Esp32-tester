# ESP32 Live Tester

A browser tool for testing electronic parts on an ESP32 without writing test code. Plug in a board, pick a part, wire it as shown, and the page reads it live and tells you pass or fail.

**Use it:** open the hosted page (GitHub Pages for this repo) in Chrome or Edge.

## What it does

- Tests 119 parts across 17 groups. Each part page shows the wiring, a live reading with a trace, the pass criteria, and a plain-language explanation of every value.
- Groups: board and bench, passive and discrete, buttons and touch, ID and access, motion and position, distance and presence, temperature pressure and humidity, air and gas, light and colour, water soil and flow, motors and drivers, relays and lamps, sound, screens and lights, radio network and location, storage and clock, power.
- Finds a part for you. An I2C part that sits at its alternate address is picked up automatically.
- Connection scan shows what is attached and which pins are held high or low before you drive anything.
- Records a live test and downloads it: a readable report (.html), readings (.csv), the raw serial log (.txt) or everything (.json), to share with a team.
- Installs the tester firmware from the page. No Arduino IDE needed.
- Includes an ESP32-CAM page.
- Quick search with `Ctrl+K` or `/`.
- Demo mode runs every part with simulated readings and needs no board.

## What it runs on

| Needs | Detail |
|---|---|
| Browser | Chrome or Edge on desktop (Web Serial). Firefox and Safari cannot talk to the board. |
| Board | ESP32 DevKit V1 (30 pin, ESP-WROOM-32) over USB. ESP32-CAM is supported on its own page. |
| Firmware | The page flashes it for you. It talks JSON lines at 115200 baud. |
| Install | None. It is one self-contained HTML file with no server and no account. |
| Data | Everything stays in your browser. Nothing is uploaded. |

## How to use it

1. Open the page. Press **Demo mode** to look around, or **Connect** with a board plugged in.
2. First time on a board: open the flasher page and install the firmware.
3. Search for a part, wire it as the Circuit tab shows, then open **Live test**.
4. Press **Run check** for a pass or fail, or **Stream live** to watch the readings.
5. Press **Record** to save the session as a report or data file.

## Notes

- A part that passes in Demo mode says nothing about a real part. Demo recordings are marked as simulated.
- Power the board from USB only while testing. Never from USB and the 5 V pin together.

## Licence

All rights reserved. The page is free to use. The code is not licensed for reuse. See `LICENSE`.
