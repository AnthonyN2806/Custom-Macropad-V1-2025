# First-Custom-Macropad-2025.

Custom Keyboard Macropad Notes


Casing

	3D models were provided for a case for the main board. While they could have worked, they would have needed to be modified due to my Pro Micro board being slightly different in design. In addition, there are a few things about the design of this case that are not preferred for my version of the board, so designing a custom case was the way to go. The casing was created using a 3D printer using PLA filament. I had decided to go for an angled construction, as it allows for more comfort and improves ease of use. The model itself was created using Fusion 360, and the pertaining files will be provided in the repository. Below are some images of the actual model and fully finished design.


Circuitry

Main Board
	The main board was actually purchased from RyanBates, and all credit to the design of the board goes to him. I believe that it is a good starting point, and allows me to become comfortable with handling circuit boards. Image of the circuit diagram is shown below.


The datasheet above has information regarding the construction of the board. The cherry MX keys are found toward the top of the board, and have support for two additional encoders in place of two MX keys. Each rotary encoder can also act as an additional key press, while also acting as an adjusting knob. Soldering the encoder jumpers allows theo be installed. LEDs were also added to each key, with a resistor for the LED power line. In general, it can be between 220 - 300 ohms, and simply protects the LEDs from too much input current, potentially burning them out.

In addition, it was stated that capacitors may be needed for each individual LED, which is why spots for them are included on the main board, based on the datasheet provided by the manufacturer. The reason for this is to make them more stable. However, the creator of the board mentions that even without said capacitors, they are stable enough, so they can be optional assuming you solder / short the connections. Lastly, diodes can also be added to each switch, as it prevents improper function when multiple keys are pressed. Since this is a macropad, and only individual switches are pressed at one time, I will not be including them, and I simply soldered the bypass.


Firmware

While some kind of firmware was provided, I decided to begin coding the firmware myself. I wanted to understand how it can be done, as it would be useful for future projects involving keyboards and switches. This was done with QMK, and they provided documentation on their website. All the files that are needed for the firmware will be kept in this repository. Here I will explain some specific parts of the code, as it may be necessary to better understand how it works.



Concluding Statement

This project was a great introduction to many aspects of electrical engineering and electronics. From soldering, to handling a circuit board, and to keyboard firmware and coding. I would love to learn even more about the internal construction and design of a keyboard. For the future, it would be great to fully design a keyboard including its layout and additional features. 















