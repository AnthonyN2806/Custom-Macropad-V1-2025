
Circuitry

**Main Board
**
The main board was actually purchased from RyanBates, and all credit to the design of the board goes to him. I believe that it is a good starting point, and allows me to become comfortable with handling circuit boards. Image of the circuit diagram is shown below.
<img width="1999" height="1545" alt="canvas" src="https://github.com/user-attachments/assets/d49a094b-a31f-418f-847a-69a7e5038590" />


  The datasheet above has information regarding the construction of the board. The cherry MX keys are found toward the top of the board, and have support for two additional encoders in place of two MX keys. Each rotary encoder can also act as an additional key press, while also acting as an adjusting knob. Soldering the encoder jumpers allows theo be installed. LEDs were also added to each key, with a resistor for the LED power line. In general, it can be between 220 - 300 ohms, and simply protects the LEDs from too much input current, potentially burning them out.

  In addition, it was stated that capacitors may be needed for each individual LED, which is why spots for them are included on the main board, based on the datasheet provided by the manufacturer. The reason for this is to make them more stable. However, the creator of the board mentions that even without said capacitors, they are stable enough, so they can be optional assuming you solder / short the connections. Lastly, diodes can also be added to each switch, as it prevents improper function when multiple keys are pressed. Since this is a macropad, and only individual switches are pressed at one time, I will not be including them, and I simply soldered the bypass.


Firmware

  While some kind of firmware was provided, I decided to begin coding the firmware myself. I wanted to understand how it can be done, as it would be useful for future projects involving keyboards and switches. This was done with QMK, and they provided documentation on their website. All the files that are needed for the firmware will be kept in this repository. Here I will explain some specific parts of the code, as it may be necessary to better understand how it works.

  In QMK, you need to define how the rows and columns relate back to the pins found on your microcontroller. Compared to the arduino IDE, the pins are labelled differently, so if a pin is has a defined label in the arduino IDE, it may not be the same in QMK. Below is a chart that shows the pin labels that are defined in QMK.


![pro_micro_pinout](https://github.com/user-attachments/assets/04f0cc52-208b-4b62-8316-9ffda8a764ea)


  For the encoders, QMK has the documentation on how to get them working. Each encoder has an A and B pin associated, and the circuit diagram that was given to me includes the associated pins. Using the diagram above, you can define them in config.h. An important note, in the rules.mk file, you only need to use ENABLE_ENCODER, and do not include ENCODER_MAP_ENABLE. This will not allow the encoders to function at all, and is used if you simply need the encoders for more complex keymaps with various layers (more than 1 function per encoder).

