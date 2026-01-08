Custom Keyboard Macropad Notes



Casing


3D models were provided for a case for the main board. While they could have worked, they would have needed to be modified due to my Pro Micro board being slightly different in design. In addition, there are a few things about the design of this case that are not preferred for my version of the board, so designing a custom case was the way to go. The casing was created using a 3D and a roll of PLA filament. The model itself was created using Fusion 360, and the pertaining files will be provided in the repository. Below you will find images of the enclosure.
<p>
<img align = "center" width="460" height="380" alt="image"  src="https://github.com/user-attachments/assets/a0e595ad-507c-4f0b-bd48-64393f082a67" />

	
</p>



Main Board


The main board was actually purchased from RyanBates, and all credit to the design of the board goes to him. I believe that it is a good starting point, and allows me to become comfortable with handling circuit boards. Image of the circuit diagram is shown below.


The datasheet above has information regarding the construction of the board. The cherry MX keys are found toward the top of the board, and have support for two additional encoders in place of two MX keys. Each rotary encoder can also act as an additional key press, while also acting as an adjusting knob. Soldering the encoder jumpers allows them to be installed. LEDs were also added to each key, with a resistor for the LED power line. In general, it can be between 220 - 300 ohms, and simply protects the LEDs from too much input current, potentially burning them out.

In addition, it was stated that capacitors may be needed for each individual LED, which is why spots for them are included on the main board, based on the datasheet provided by the manufacturer. The reason for this is to make them more stable. However, the creator of the board mentions that even without said capacitors, they are stable enough, so they can be optional assuming you solder / short the connections. Lastly, diodes can also be added to each switch, as it prevents improper function when multiple keys are pressed. Since this is a macropad, and only individual switches are pressed at one time, I will not be including them, and I simply soldered the bypass.


Firmware

	
While some kind of firmware was provided, I decided to begin coding the firmware myself. I wanted to understand how it can be done, as it would be useful for future projects involving keyboards and switches. This was done with QMK, and all the files related to the firmware will be kept in this repository. Below is a correct pinout diagram.

<img width="476" height="304" alt="image" src="https://github.com/user-attachments/assets/cd0b4559-e0f5-4bd2-97c5-cf3e06ea0e6f" />

For the encoders, QMK has the documentation on how to get them working. Each encoder has an A and B pin associated, and the circuit diagram that was given to me includes the associated pins. Using the diagram above, you can define them in config.h. An important note, in the rules.mk file, you only need to use ENABLE_ENCODER, and do not include ENCODER_MAP_ENABLE. This will not allow the encoders to function at all, and is used if you simply need the encoders for more complex keymaps with various layers (more than 1 function per encoder).

Experienced Complications and Issues
One big problem that is occurring is that only one LED is currently being turned on, that being the first one in the chain. From what I have gathered, the main issue is most likely the chain being disrupted, and none of the other LED’s are currently being lit. I checked for continuity between each set of two LED’s, and it seems that between the first and second LED, continuity is broken (Multimeter beeps). For that reason, I am assuming it needs to be replaced.

Concluding Statement

This project was a great introduction to many aspects of electrical engineering and electronics. From soldering, to handling a circuit board, and to keyboard firmware and coding. I would love to learn even more about the internal construction and design of a keyboard. For the future, it would be great to fully design a keyboard’s layout and add additional innovative features.











References 

Various links and sources that I deemed important to the project will be held below.

https://golem.hu/article/pro-micro-pinout/ 
https://docs.arduino.cc/retired/hacking/hardware/PinMapping32u4/ 


