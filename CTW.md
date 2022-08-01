### [BACK TO HOMEPAGE](https://ejwilcoxprojects.github.io)

<h1 align="center">From EAGLE to Wegstr</h1>



This tutorial will provide a step-by-step guide on the CAD to CAM process, in this case using your EAGLE design as a starting point. Please note that the values advised are solely guidelines and each milling machine will work at its own capacity.

In addition, this tutorial covers top layer PCB only. In the future, this tutorial may expand to accommodate for more complex circuits.

NECESSARY SOFTWARE TO FOLLOW THIS TUTORIAL:

-EAGLE
-FLATCAM
- (Optional) GERBER VIEWER
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

At this point you can flip your board so that the copper side of the board is a mirror to the side you will be putting the components onto.

![drill view](https://i.ibb.co/3hg929D/Drill-View.png)

![view project](https://i.ibb.co/FhJ4L9g/View-Project.png)

![view gerber](https://i.ibb.co/kgLsdR5/Gerber-Object-Selected.png)

![isolation geometry](https://i.ibb.co/RC8y0v6/Isolation-Tool-View.png)

![isolation to cnc](https://i.ibb.co/C7hHVBM/Generate-CNC-Job-Object-Isolation-Geometry.png)

![cnc look](https://i.ibb.co/YWYDBdc/CNC-View.png)

![exc 1](https://i.ibb.co/gZ3yzwt/Excellon-object-1.png)

![exc 2](https://i.ibb.co/wR3YTWL/Excellon-object-2.png)

![drill path](https://i.ibb.co/h7H2Yyz/image-2022-08-01-110041317.png)

![cutout choose](https://i.ibb.co/hfthMfd/image-2022-08-01-110249398.png)

![cutout tool](https://i.ibb.co/MSJGDD8/cutout-generate-cnc.png)

![view complete](https://i.ibb.co/pX4b0kV/Board-complete.png)

![3 cnc](https://i.ibb.co/NSrT4xg/cnc-list.png)

![open wegstr](https://i.ibb.co/MDdSBVr/List-in-wegstr.png)

![wegstr path](https://i.ibb.co/svS7rZb/wegstr-top.png)


