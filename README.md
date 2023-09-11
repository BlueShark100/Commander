# Commander (code name Sirius 02)
Commander is essentially a little programable toy you can bring around to practice coding and have fun with if you not home with your usual projects. It's main pourpose and code provides a menu that allows you to nivage through differnt OS tips and tricks along with Keybaord shortcuts and thier descriptions. Its like a little helper to make you a pro at navigating your computer faster and easier. I'm writing the code so respective to MacOS commands but feel free to interprete your own commands and edit the lists within the code to make your own version of the Commander. You can go as far as writing your own code for the board too! I'll provide pin assingments on an example code for pong on the project (after I finish the primary code). 

This project includes a builtin D-Pad, a 128*64 OLED display on an I2C connection, and side-fireing WS2812B LEDs to light up the case!

# Current status of the project (still approaching V1)

### The Quick Version
- Still completing README.md
- Completed reference animations
- Coding menu animation
- Designing new board with alternate MCU
- Case is hard to take apart

### Code
This is currently in developement. I'm working to complete V1 still and if you happen to come across this repo feel free to help out. Right now I'm working on getting the menu animation completed on the display by using lists with coodinates for each element. As it goes through the loop it will "animate" the menu into creation. But i'm having an issue with the two top lines for the top bar of the menu where it's refusing to work properlly when using i to select the corresponsing coordinate for the line. No syntax errors, not running out of memory (I've tried this by writing more objects that arent the line to the display and they work fine), the list and i are properly defined, and its not going out of range of the list. 

### Board
Originally I was planning on using the ATmega16U2 however I kept running into issues trying to find custom firmware to have it work as the primary MCU on the board. This MCU is commonly found on the Arduino Uno used as a USB to serial converter. I found a github repo called HoodLoader that aims to use this MCU as a microcontroller along side the primary MCU of the board (ATmega328p) however I honestly could never figure out how to get it to work with a standalone ATmega16U2. If anyone knows how to get the ATmega16U2 to run as a standalone MCU that would be the primary goal since that would allow for USB HID support

I'm working on a new board that will be using the CH340 USB to serial converter (using the RedBoard Qwuicc schemtic for quidence since the datasheet is all in chineese) and the ATmega328p. There will be no USB HID support but you should be able to program the board directly from a USB and the Arduino IDE. I'm considering adding an EEPROM module to store some of the byte arrays so that it doesnt take up program memory space. The specific EEPROM would be the Microchip Tech AT24C32D-SSHM-T, its got 32Kbits of storage (4Kbytes) and uses and I2C communication. The second version of the board will also have probing pads and some solder jumpers to make the board more flexible in use after its been manufactured.

If you are an electrical engineer and know how to do this please reach out. Everything I know about designing PCBs and cuictes has been primarily self taught so I would love to learn form an expert. 

### Casing
I'm printing the casing out of a sparkling black PLA from Microcenter. This filement gives a great effect with the sparkles gaving some extra interest to the surface without being too distracting. It also slightly transparnt when printed thin enough which allows the LEDs to shine through and illumiane the components inside while looking super cool! 

Working on a better machenism to connect the bottom plate sercurely while still being able to take it out easily. 

### Prototyping
I'm protyping the project on a breadboard while I go. That way I can continue working on the code while I wait for a working board to arrive. This section is mainly to put some images of what it looks like so far. I also have the images so there something cool to look at instead of a bunch of text in the README file. 

Heres a test of what the LEDs within the Case might look like. **these are full sized LEDs so its way brighter that what its actually going to be on the board but worth checking out**

![Test of colors in the Case](/Images/Colors1.jpeg)
![Test of colors in the Case](/Images/Colors2.jpeg)
![Test of colors in the Case](/Images/Colors3.jpeg)
![Test of colors in the Case](/Images/Colors4.jpeg)
![Test of colors in the Case](/Images/Colors5.jpeg)

# How do I get one of my own?
**THIS PROJECT IS UNCOMPLETE AT THE MOMENT. The code and files are not finalised and may not work as inteded. Especialy right now the project WILL NOT WORK.**

The commander project is a PCB at heart. You'll need to order the board from a manufacturer youself. On top of the board you'll also have to order the components reqired for the circuit from lcsc. These components and the gerber files for the PCB can be found under the PCB files. There will be a BOM that you can use to find the components quickly and easily in lcsc, the quantities will be defined for 1 board only but feel free to edit the quantities later if you want more boards or extra components.

I'll write another quide for what each of the IDs are on the board. For example that "R3" is a 330 ohm resistor and C11 is a 1uF capacitor. 

# Extra tid bits
Heres the original sketch I drew when I first had the idea
![Test of colors in the Case](/Images/Idea_sketch.jpeg)

