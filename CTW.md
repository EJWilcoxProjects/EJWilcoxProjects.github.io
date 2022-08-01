### [BACK TO HOMEPAGE](https://ejwilcoxprojects.github.io)

<h1 align="center">From EAGLE to Wegstr</h1>



This tutorial will provide a step-by-step guide on the CAD to CAM process, in this case using your EAGLE design as a starting point. Please note that the values advised are solely guidelines and each milling machine will work at its own capacity.

In addition, this tutorial covers top layer PCB only. In the future, this tutorial may expand to accommodate for more complex circuits.

NECESSARY SOFTWARE TO FOLLOW THIS TUTORIAL:

-EAGLE
-FLATCAM
-GERBER VIEWER (Optional)
-WEGSTR

# 1. EAGLE

Once your schematic and board has been downloaded or designed, the appropriate files must be taken from your EAGLE board to be used externally to the program.

Your first step in this process is to maneuver over to FILE and CAM PROCESSOR. This will be found at the top left of your display.

![Eagle](https://i.ibb.co/9v0s00C/Eagle-cam.png)

Once you have clicked on CAM PROCESSOR, a list of files will appear. The most important for this tutorial are the GERBER and DRILL FILES, more specifically the single DRILL FILE and TOP COPPER GERBER.

![Eagle Process](https://i.ibb.co/Fn1K4dC/Process-job.png)

At this point, you can click Process Job, the files will be found within EAGLE under CAMOUTPUTS.

# 2. Opening Files in FlatCAM

EAGLE can now be closed, and FlatCAM can be opened.

FlatCAM is used to create the cnc files which will tell the Wegstr machine which paths and coordinates to follow in the milling stage.

On the top left of the display, click on FILES and OPEN GERBER.

![open gerber](https://i.ibb.co/hV4rqY3/Open-Gerber.png)

Now find your CAMOUTPUTS folder which contains the ASSEMBLY, DRILLFILES and GERBERFILES FOLDERS.


![select camout](https://i.ibb.co/C0PdTx4/Select-CAM.png)

Select the GERBERFILES folder.

![select gerber](https://i.ibb.co/K7JDfp0/image-2022-08-01-103813222.png)

Click on COPPER_TOP. This will bring the COPPER_TOP GERBER FILE into the FlatCAM project.

![select pcb layer](https://i.ibb.co/BtJ5FPT/image-2022-08-01-103935528.png)

Below is an example board of what you will see, however your circuit will look different. Make sure to compare the location and look of your board to your EAGLE board to make sure everything seems correct.

![view board](https://i.ibb.co/LxQHrRS/Gerber-View.png)

Now that the GERBER FILE has been brought in successfully, the same steps will be repeated except this time for the DRILL FILES. 

Click on OPEN EXCELLON

![open excellon](https://i.ibb.co/hZBVL7M/image-2022-08-01-104349251.png)

Find the CAMOUTPUTS FOLDER again. This time, go to DRILLFILES and click the DRILL FILE present within the folder.

![select drill](https://i.ibb.co/C2xxDtF/image-2022-08-01-104505468.png)

On the board should appear red circles like below. 

Make sure that all holes are aligned with the board correctly. If there is a mistake and the scaling is wrong, a few things can be modified to potentially fix the issue.

One is that Eagle may put a '%' at the beginning of the EXCELLON file. This can be modified by opening the DRILL.xln file with Notepad and removing the first '%' at the start of the text.

Secondly, I managed to fix the error reading the .xln file by opening it first in GERBER VIEWER, then saving it again (overwriting the previous or renaming if you wish). 

After some troubleshooting, the holes should align with the board.


![drill view](https://i.ibb.co/3hg929D/Drill-View.png)

At this point you can FLIP your board so that the copper side of the board is a mirror to the side you will be putting the components onto. You can find the option to FLIP in the OPTIONS tab.

# 3. Modifying .gbr file parameters

![view project](https://i.ibb.co/FhJ4L9g/View-Project.png)

On the left of the project, the .gbr and .xln files should be visible as seen above.

Click on the .gbr file and move to the SELECTED panel next to PROJECT

![view gerber](https://i.ibb.co/kgLsdR5/Gerber-Object-Selected.png)

Once a panel with GERBER OBJECT at the top is visible, click on ISOLATION ROUTING in the TOOLS submenu.

![isolation geometry](https://i.ibb.co/RC8y0v6/Isolation-Tool-View.png)

The TOOL PANEL will change to say ISOLATION TOOL. 

This is the point where parameters can be changed to suit your board manufacture and milling machine specifics.

**KEEP IN MIND THAT THE PARAMETERS VISIBLE IN THE SCREENSHOTS SHOULD NOT NECESSARILY BE REPLICATED**

-Cut Z: -0.0750

-Passes: 2

-Overlap 25.0000 %

FOR MORE THAN 1 PASS, MAKE SURE TO CLICK **COMBINE**

![isolation to cnc](https://i.ibb.co/C7hHVBM/Generate-CNC-Job-Object-Isolation-Geometry.png)

Unlike in the screenshot, for the Wegstr machine that I have worked on, I prefer to change the following:

-Cut Z: to -0.0750
-Travel Z: 1.0000
-Feedrate X-Y: 80.0000
-Spindle Speed: 10000

Next click GENERATE CNCJOB OBJECT at the bottom of the panel.

![cnc look](https://i.ibb.co/YWYDBdc/CNC-View.png)

The tracks will be highlights with information at places where the milling machine will travel to. Faintly, the path can be seen in yellow.

Additionally, on the left, in CNC JOB, a new CNC FILE should be visible.

# 4. Modifying .xln file parameters

Simply, like the last .gbr FILE. Move back to project and click on the .xln FILE and move over to the SELECTED TAB.

![exc 1](https://i.ibb.co/gZ3yzwt/Excellon-object-1.png)

A TOOLS TABLE should show the variety of drill diameters for the board. This is taken from the component information from EAGLE, so if all the components chosen are accurate, nothing will need changed.

Depending on the thickness of your board and milling machine capabilities, once again a few parameters may need modified accordingly. Experiment and find what works best for your machine.

Here are a few changes I make:

-Cut Z: -2.5
-Travel Z: 1.0000
-Feedrate Z: 80.0000
-Spindle Speed: 10000

![exc 2](https://i.ibb.co/wR3YTWL/Excellon-object-2.png)

If you wish to change your drill diameter in the drilling process, make sure to tick TOOL CHANGE Z. (15.0000 may not provide enough height to change heads, so 25.0000 may be more appropriate).

Finally, click GENERATE CNCJOB OBJECT

![drill path](https://i.ibb.co/h7H2Yyz/image-2022-08-01-110041317.png)

Thicker yellow lines will show on the preview to confirm that the step was complete accordingly. 

A new CNC FILE should appear in PROJECTS.

# 5. CUTOUT file parameters

The last and optional step is to create a last step to tell the machine to cut out the perimeter of the board.

Click on the .gbr FILE from the beginning in projects, and once highlighted, go to TOOL and CUTOUT PCB

![cutout choose](https://i.ibb.co/hfthMfd/image-2022-08-01-110249398.png)

If cutting out your PCB entirely, here are a few changes that could be useful to change.

-Cut Z: -2.5
-TICK MULTI-DEPTH and set to 0.5000
-Travel Z: 1.0000
Feedrate X-Y: 80.0000
Spindle speed: 10000


![cutout tool](https://i.ibb.co/MSJGDD8/cutout-generate-cnc.png)

Once all parameters have been changed, for the final time click GENERATE CNCJOB OBJECT.

![view complete](https://i.ibb.co/pX4b0kV/Board-complete.png)

A thick perimeter will appear around the preview showing the CUTOUT path.

![3 cnc](https://i.ibb.co/NSrT4xg/cnc-list.png)

As seen on the left list in PROJECTS, the 3 CNC files will be listed in CNC JOB. 

Right click on each cnc file and save them.

You can now close FlatCAM and open Wegstr.

# 6. Wegstr

Make sure a copper pcb is clamped and centered on the milling machine.

Measure and provide enough space for the milling machine to cut out the designed circuit.

A tip to calibrate the drillbit close to the board is to bring down the head until it touches a piece of paper between the copper and the drillbit. Slowly remove the paper and make the co-ordinates 0.

Once the head is at zero and the machine is ready to cut, open up your files. Start with the order in which we created the cnc files.

![open wegstr](https://i.ibb.co/MDdSBVr/List-in-wegstr.png)

When you open the first cnc file, you will see the design and path appear again. Make sure that everything in the path is correct and you can start your manufacturing.

![wegstr path](https://i.ibb.co/svS7rZb/wegstr-top.png)

Repeat for the drilling and cutout, making sure to return to 0 after each step is complete.

**Congratulations** Your board is complete.


