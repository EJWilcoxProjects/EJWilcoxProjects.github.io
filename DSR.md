### [BACK TO HOMEPAGE](https://ejwilcoxprojects.github.io)

<h1 align="center">Doublestop Rocker</h1>


This project is inspired by [Jeremy Bell's Doublestop Rocker](https://www.youtube.com/watch?v=v0ewoMDygK0) which can be mounted to a guitar or sit on its own. My goal was to find a way to closely replicate Jeremy's original design, but provide several designs capable of working in a similar manner. On top of this, developing it further with the use of 3D printing, creating a new Max patch with the aid of collaboration, and repurposing the Teensy USB_MIDI Buttons sketch.

*At the end of this page, I will also provide a list to the different designs and the files so that you can print and try them out.*

The way in which my Doublestop rocker functions is similar to Jeremy's in the use of Teensy as the midi controller. Each side of the Doublstop rocker has a conductive pad connecting to two of the digital pins on the Teensy board. In Jeremy's case, it looks like his top rocking piece is one conductive surface connected to ground, and the base is connected to two different pins.

# Early Doublestop 3D Designs

![rocker first](https://i.ibb.co/CzrPGDZ/Double-Stop-Rocker-Top-Variation-3-2022-Jul-31-10-47-06-AM-000-Customized-View6365680705-png-alpha.png)

Above is my first design of the top rocking pad with all established indents for magnets and coins (which will be discussed further in the page).
This design uses horizontally printed pivots that slot into two 'U' shaped holders on the rocker base shown below. Although these small plastic rods seem fragile, this design holds up very well aswell as still rocking smoothly after constant use. 

![rocker bottom](https://i.ibb.co/12x50jS/Rocker-base-design-dupe-2022-Jul-31-10-33-59-AM-000-Customized-View11890239674-png-alpha.png)

These designs use both elastic bands and coin neodymium magnets as a way to keep them balanced and springing back to a neutral floating position. The elastic bands can actually provide the same effect by themselves, and better as a budget build.

![rocker top](https://i.ibb.co/JRQ6S5J/Double-Stop-Rocker-Top-Variation-3-bar-2022-Jul-31-10-32-04-AM-000-Customized-View21107458359-png-al.png)

Above you can see a variation of the rocker top design, still with lots of magnet slots, and this one requires it as it isn't held in with elastic bands, instead the magnets keep the rocker repelling at each side. Simply requires using superglue to glue the magnets in with polarities causing base and top to repel against eachother. A simple 2D CAD file can be made to laser cut out an MDF cover for the magnets, however this is redesigned later due to further simplification of design.

# Early 4 Way Rocker 3D Designs

On the chance that this device would be used off a guitar and rather sit at a desk, the idea of having more than two sides that could be flicked was quite interesting. 

I developed a joiner, which would sit in the open 'U' shaped base, and allow pivoting in the perpendicular direction.

![4 rocker joiner](https://i.ibb.co/SxdJfRG/Double-Stop-Rocker-joiner-2022-Jul-31-10-33-18-AM-000-Customized-View6896141530-png-alpha.png)

On top of this would sit a variation 4 way rocker, without any magnets as this version would rely solely on the elastics, keeping cost lower.

![4 rocker](https://i.ibb.co/w0r3HPX/Rocker-base-design-dupe-2-2022-Jul-31-10-36-46-AM-000-Customized-View1814049647-png-alpha.png)

![4 rocker 2](https://i.ibb.co/zsv0frX/Rocker-base-design-dupe-2-2022-Jul-31-10-38-13-AM-000-Customized-View3284865224-png-alpha.png)

As seen above, the joiner doesn't add too much height on to the design to make it not function, and let the design move in 4 (and arguably 8 directions, providing the possibility of diagonal movement).

The concept of having AND logic in this rocker design will be something I will be experimenting with post-project.

# Final Rocker 3D Designs

![rocker combined](https://i.ibb.co/syrTJrt/Rocker-base-design-dupe-bar-2022-Jul-31-10-31-40-AM-000-Customized-View23189622749-png-alpha.png)

As is visible, the middle has been reinforced and rounded. This came from post-testing realisations, a more convex shape provides the fingers an easy surface to roll off.

![round 4 way](https://i.ibb.co/vJdGcMw/Rocker-base-design-dupe-2-2022-Jul-31-10-46-02-AM-000-Customized-View13011772815-png-alpha.png)

The top piece for the 4 way rocker has a similar modification, however with slots to accommodate to elastic bands. This two way, two tier elastic band setup allows the joiner and top piece to stay in place, whilst also restricting its motion to bend, ultimately wanting to settle centrally.

# Doublestop Rocker Max Patch Variations

The first max patch is a demonstration of the midi input being read with 'high' and 'low' seen as '99' and '0' respectively. This is the same across all of the max patches. The other numbers, correspond to the midi note that the .ino file has assigned to the digital pins of the Teensy. These notes can be changed to midi '0', '1', or '2' and so on. This patch was made with the help of my [module supervisor](https://miguel-ortiz.com), which I would then go on to adapt.

![max original](https://i.ibb.co/Xj3N65F/image-2022-08-01-132905863.png)

This example has two sound files activated by the toggle buttons in the patch, with a central continuous looping sound file. 

Once my tests with the rocker provided the expected outcome from this patch, I could then adapt it for live audio in, just like in Jeremy's demonstration.

![max live audio](https://i.ibb.co/Yy6F9Nd/3rd-Patch.png)

Above is the max patch I adapted from the previous, now using gates and experimenting with different effect plugins. These gates toggle the signal going to the output, and provides the same chopped up sound achieved in Jeremy's video.

# Doublestop Rocker Max Patch Variations

Very similar to the first patch, this four way patch provides a duplication of the top half of the patch and works in a similar manner but with two more midi notes. The midi notes assigned this time were 0, 1, 2 ,3 solely because these are much simpler to keep track of. Originally it was to not interfere with any other midi inputs, but this changed when I began to assign individual midi inputs to different sections of the patch.

![max original 4](https://i.ibb.co/6n2dPTq/2nd-Patch.png)

Below is the midi and audio control interface for 4 Way Rocker. This design needs more refinement but functions well. Midi ins have been assigned so that the midi keyboard controlling the two synthesisers I connected to the laptop don't interfere with the Teensy Midi USB connection. 

![max midi control 4](https://i.ibb.co/bBMXckN/4th-Patch.png)

# Physical Builds

Below are the current physical Doublestop and 4 Way Rocker builds. This Doublestop uses elastic and magnets along with the MDF cover. 

Within the hollow Rocker base sits the Teensy 4.0, along with two neodymium magnets at each end to repel the top rocking platform.

![double stop creation](https://i.ibb.co/4Pf6RkM/DSC-3881.jpg)

This 4 Way Rocker design below has removeable polymorph covers to allow more ergonomic toggling of each of the four sides.

![4 way creation](https://i.ibb.co/N7byqQV/DSC-3883.jpg)


# Build Instructions and List of Parts

In the link below contains the necessary .stl, .ino
[Click Here](https://drive.google.com/drive/folders/1H8cQ9-BR39GN7Wlx6rk8J9TUlsvbFm7x?usp=sharing)













