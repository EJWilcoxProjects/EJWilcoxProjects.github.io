### [BACK TO HOMEPAGE](https://ejwilcoxprojects.github.io)






<h1 align="center">Piezo Buffer Project</h1>




The piezo buffer board is inspired heavily by [Scott Helmke's](http://scotthelmke.com/Mint-box-buffer.html) mint-box piezo buffer.

It is important to premise that although there were personal expenses put into the project, still lack of certain components rendered this project impossible to test. Instead, this piezo buffer project will look at the design and outcome of the board. 

Additionally, further to be discussed is component substitution and a continuation of the CAM and CAD process in the CAM step-by-step guide.

![Scott's diagram](https://i.ibb.co/zFz0LWb/Mint-box-buffer-schematic.jpg)

Seen above, Scott's schematic is centered around a JFET 2N5457; a transistor used for tone modulation, amplification and more. In a simplified way to understand this circuit, the audio signal travelling through has a gain switch for two different options. The 2N5457 is used to retain bass and maintain a better level of fidelity than without any pre-amp or buffer.

Misunderstanding the diagram early on in the process, I had created an initial large prototype with a 3D casing.

![Piezo Buffer Early](https://i.ibb.co/Mn0X93Z/piezob-buffer-holder-2-2022-Jul-31-10-32-46-AM-000-Customized-View4599899894-png-alpha.png)

A few substitutions were made for components, this led testing to become unsure, whether the components or connections were incorrect, it led to continuing on with a redesign of the PCB, using the (in theory) useable substitutions to replace the components used in Scott's version. 

-512-2N5457	2N5457

-140-PF1H303K	0.033uF polyester

-140-PF1H104K	0.1uF polyester

-74-199D10V4.7A	4.7uF tantalum

-140-50N5-200J	20pF ceramic

-291-4.7M	4M7 resistor

-291-10M	10M resistor

-291-220K	220K resistor

-291-10K	10K resistor

-502-112B	Stereo jack

-123-5006-GR	9v battery snap


Above is a list of the original components, a few of these were substituted.

The two polyester capacitors were replaced with one aluminium electrolytic and one ceramic of same values. This is possibly the most to blame for the final design not functioning, but that requires further tests and the appropriate components to begin with.

In Scott's description, he clarifies that the 20pF ceramic capacitor is replaced with a 1pF capacitor. For this project, I ended up using a 22pF ceramic which should still work.

The stereo jack connections used by Scott are replaced with MJ-63022A Mono Female connectors.

![My sch](https://i.ibb.co/g9B03QX/Piezo-Buffer-Sch.png)

This schematic is produced in EAGLE with close approximation to Scott's original design.

![My brd](https://i.ibb.co/MZrHC4L/Piezo-Buffer-Brd.png)

The board itself is approximately half of the first design, compressing the tracks and providing a more compact final board.
One issue with this design was that due to the boards smaller design and track width (Which will be discussed more in EAGLE to Wegstr), Wegstr milling machine doesn't have much room for error. 

![My concept](https://i.ibb.co/n3bxJ18/piezo-holder-2022-Jul-31-10-29-57-AM-000-Customized-View26086548375-png-alpha.png) 

The concept board was then assembled inside of its case, making sure all components had enough space and that the female connectors did not interfere with the designed enclosure.

At this point, the board could be constructed and encased.

![My build](https://i.ibb.co/nsqPhFy/DSC-3889.jpg)

Above is the final design, however unfortunately the board does not function, and without the appropriate components, it's difficult to know what variable prevents this design from not working. In any event, if you decide to take on this project yourself, please get in touch with feedback about the design and what changes you made.

Please follow the [Eagle to Wegstr tutorial](http://EJWilcoxProjects.github.io/CTW.html) to see the step-by-step process to see more information on how the board was made.




