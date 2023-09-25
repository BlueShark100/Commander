# Commander (code name Sirius 02)
Commander is essentially a little programable toy you can bring around to practice coding and have fun with if you not home with your usual projects. It's main purpose and code provides a menu that allows you to navigate through different OS tips and tricks along with keyboard shortcuts and their descriptions. Its like a little helper to make you a pro at navigating your computer faster and easier. I'm writing the code so respective to MacOS commands but feel free to interpret your own commands and edit the lists within the code to make your own version of the Commander. You can go as far as writing your own code for the board too! I'll provide pin assignments on an example code for pong on the project (after I finish the primary code). 

This project includes a builtin D-Pad, a 128*64 OLED display on an I2C connection, EEPROM with 4Kbytes, and side-fireing WS2812B LEDs to light up the case!

# Current status of the project (Waiting for Second revision of the PCB to arrive)

### The Quick Version
- Still completing README.md
- Completed reference animations
- Coding menu animation
- Waiting for new board using ATmega328p
- Case is hard to take apart

### Code
This is currently in development. I'm working to complete V1 still and if you happen to come across this repo feel free to help out. Right now I'm working on getting the menu animation completed on the display by using lists with coordinates for each element. As it goes through the loop it will "animate" the menu into creation. Working on a solution to avoid overflowing the display buffer which may be the cause of unexpected behavior when running the animations. Defined the animations as separate functions to avoid clutter at the top of the program where the primary functional code is.

Almost done creating the static menu screen, once that is complete I can start working on navigation through folders and commands

### Board
Originally I was planning on using the ATmega16U2 however I kept running into issues trying to find custom firmware to have it work as the primary MCU on the board. This MCU is commonly found on the Arduino Uno used as a USB to serial converter. I found a github repo called HoodLoader that aims to use this MCU as a microcontroller along side the primary MCU of the board (ATmega328p) however I honestly could never figure out how to get it to work with a standalone ATmega16U2. If anyone knows how to get the ATmega16U2 to run as a standalone MCU that would be the primary goal since that would allow for USB HID support

I'm waiting to order/receive a new board that will be using the CH340 USB to serial converter (using the RedBoard Qwuicc schematic for guidance since the data sheet is all in Chinese) and the ATmega328p. There will be no USB HID support but you should be able to program the board directly from a USB and the Arduino IDE. I'm adding an EEPROM module to store some of the byte arrays so that it doesn't take up program memory space. The specific EEPROM would be the Microchip Tech AT24C32D-SSHM-T, its got 32Kbits of storage (4Kbytes) and uses and I2C communication. The second version of the board includes output pins for the currently unused Arduino pins for expandability and a solder jumper for the Write Protect configuration on the EEPROM module.

If you are an hardware engineer and know how to do this please reach out. Everything I know about designing PCBs and circuits has been primarily self taught so I would love to learn form an expert. 

### Casing
I'm printing the casing out of a sparkling black PLA from Microcenter. This filament gives a great effect with the sparkles giving some extra interest to the surface without being too distracting. It also slightly transparent when printed thin enough which allows the LEDs to shine through and illuminates the components inside while looking super cool! 

Working on a better mechanism to connect the bottom plate securely while still being able to take it out easily. 

### Prototyping
I'm prototyping the project on a breadboard while I go. That way I can continue working on the code while I wait for a working board to arrive. This section is mainly to put some images of what it looks like so far. I also have the images so there something cool to look at instead of a bunch of text in the README file. 

Heres a test of what the LEDs within the Case might look like. **these are full sized LEDs so its way brighter that what its actually going to be on the board but worth checking out**

![Test of colors in the Case](/Images/Colors1.jpeg)
![Test of colors in the Case](/Images/Colors2.jpeg)
![Test of colors in the Case](/Images/Colors3.jpeg)
![Test of colors in the Case](/Images/Colors4.jpeg)
![Test of colors in the Case](/Images/Colors5.jpeg)

# How do I get one of my own?
**THIS PROJECT IS INCOMPLETE AT THE MOMENT. The code and files are not finalized and may not work as intended. Especially right now the project WILL NOT WORK.**

The commander project is a PCB at heart. You'll need to order the board from a manufacturer yourself. On top of the board you'll also have to order the components required for the circuit from lcsc. These components and the Gerber files for the PCB can be found under the PCB files. There will be a BOM that you can use to find the components quickly and easily in lcsc, the quantities will be defined for 1 board only but feel free to edit the quantities later if you want more boards or extra components.

I'll write another guide for what each of the IDs are on the board. For example that "R3" is a 330 ohm resistor and C11 is a 1uF capacitor. 

# Extra tid bits
Heres the original sketch I drew when I first had the idea
![Test of colors in the Case](/Images/Idea_sketch.jpeg)

