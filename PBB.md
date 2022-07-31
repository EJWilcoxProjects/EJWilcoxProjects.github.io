### [BACK TO HOMEPAGE](https://ejwilcoxprojects.github.io)




<br>

<h1 align="center">Piezo Buffer Project</h2>




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


Above is a list of the original components.



