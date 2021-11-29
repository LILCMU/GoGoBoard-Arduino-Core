# The GoGo Board 6.x firmware for an Arduino Core
This firmware enabled default features of 3 digital ports on arduino core side (bottom-left of the board). This consists of temperature / humidity (SHT31), ultrasonic distance (Grove ultrasonic) and rgb leds (Grove NeoPixels).

---

## Usage with G-message to control or getting value from Arduino Core
- Temperature (sensor value)
  - G-message key : `temperature`
- Humidity (sensor value)
  - G-message key : `humidity`
- Ultrasonic distance (sensor value)
  - G-message key : `distance`
- RGB LEDs (peripheral control)
  - **set pixels number / count**
    - G-message key : `pixels:count`
    - G-message value : `<number of pixels on strip>` (Max at 255 LEDs)
  - **set pixel brightness**
    - G-message key : `pixels:brightness`
    - G-message value : `<brightness percentage>` (0 - 100% brightness)
  - **set pixels color**
    - G-message key : `pixels:color`
    - G-message value : `<color number>` (0 - 20 predefined colors)
  - **set pixels pattern**
    - G-message key : `pixels:pattern`
    - G-message value : `<pattern number>` (0 - 4 predefined patterns)

### Predefined colors and patterns
> Colors
> - `0` : Black
> - `1` : Red
> - `2` : Green
> - `3` : Blue
> - `4` : White
> - `5` : Cyan
> - `6` : Yellow
> - `7` : Magenta
> - `8` : Navy
> - `9` : Dark green
> - `10` : Dark cyan
> - `11` : Maroon
> - `12` : Purple
> - `13` : Orange
> - `14` : Pink
> - `15` : Olive
> - `16` : Bright red
> - `17` : Light grey
> - `18` : Dark grey
> - `19` : Green yellow
> - `20` : Light green

> Patterns
> - `0` : Static color
> - `1` : Wipe color
> - `2` : Theater chase
> - `3` : Rainbow
> - `4` : Rainbow theater chase

### Example
- [Arduino Core Usage](https://code.gogoboard.org/#/program/1e27fa9b-e5a8-4dbc-8354-099038e49f82) : This will showing distance from ultrasonic on GoGo screen, if temperature is more than 27 celcius - GoGo beeping, and RGB LEDs wiping to `red` color with 20% brightness on 25 LEDs count.

---

## How to download / update firmware to Arduino Core ?
This firmware can be downloaded to the Arduino Core by using `GoGo Updater` program

> GoGo Updater Installer : [Download link](https://github.com/MomePP/gogo-updater-electron/releases/latest)

### Update Arduino Core firmware procedure
- Open `GoGo Updater` program. (must be close `GoGo Plugin` first, if it running)
- Download latest Arduino Core firmware binary file : [here](https://github.com/LILCMU/GoGoBoard-Arduino-Core/releases/latest)
- Connect Micro-USB port at the back of GoGo Board to your computer
- Press and hold a button(ARD BOOT) near Micro-USB port while turning on the GoGo Board's power switch
- On `GoGo Updater`, browse the downloaded firmware file by using STM browse button (connection status says `Not Connected`, it's a normal behavior)
- Click on `Update` button the program will performs updating

After updating, you should see the Red LED at the back of GoGo Board(near STM Arduino Core chip) blinking every 1 second
