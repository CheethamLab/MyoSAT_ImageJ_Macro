## Creating Mask Images for MyoSAT with GIMP



The purpose of this guide is to show how to create mask images for use with MyoSAT using the open source program GIMP. A mask image is white in areas with muscle fibers to be analyzed (foreground) and black in areas that do not contain fibers or that should otherwise not be analyzed (background). In ImageJ, black corresponds to a value of 0, and white to a value of 65535 (max value). Only fibers in the white areas will be analyzed. Thicker sections, areas of connective tissue or areas where the fibers are not clearly visible can result in incorrect measurements. For more accurate results, it is best to include as much of these areas as possible in the background.

GIMP is available for download at: https://www.gimp.org/downloads/

1.	Load image into GIMP (‘File’ > ‘Open...’)


![](Documentation/img/img_mask_guide/mask_guide_1.jpg)



2.	Open the ‘Scale Image’ menu from the top menus: 	‘Image’ > ‘Scale Image...’
Record the original resolution in pixels of the image, as this will be needed to later restore it to the exact resolution. Change the Image Size tab to %, set height and width to 25% and press Scale in the bottom right.
<br/>

![](Documentation/img/img_mask_guide/mask_guide_2.jpg) 
<br/><br/><br/>
![](Documentation/img/img_mask_guide/mask_guide_3.jpg) 
<br/><br/><br/>
![](Documentation/img/img_mask_guide/mask_guide_4.jpg) 
<br/><br/>

3.	From the top menus select: ‘Layer’ > ‘Transparency’ > ‘Alpha Channel’
<br/>

![](Documentation/img/img_mask_guide/mask_guide_5.jpg) 
<br/><br/>
 
4.	Remove the background (areas that are not going to be used in the analysis) using the fuzzy and erasure tools. If either tool is not erasing, it is likely because the correct channel isn’t selected. Select ‘Channels’ from the menu on the right side of the screen (In between ‘Layers’ and ‘Paths’. Right click on Alpha, and select ‘Channel to Selection’. 
<br/>

![](Documentation/img/img_mask_guide/mask_guide_6.jpg) 
<br/><br/>

4a. Fuzzy Tool: Select the fuzzy tool (looks like a star and line) from the set of tools in the upper left hand side of screen. Click over the image and hold down. Move the pointer to the right of the screen to increase the selected area or to the left to decrease the area. Release the mouse when the desired area is selected. This can be manually adjusted in the ‘Threshold’ tab on the middle left side of the screen. When the desired area is selected press delete (Fn & delete on Mac, or alternatively Command & x), to remove the selected area. 

 <p align="center">
  <img src="https://github.com/CheethamLab/MyoSAT_ImageJ_Macro/blob/master/Documentation/img/img_mask_guide/icon_wand.jpg" />
</p>


 ![](Documentation/img/img_mask_guide/mask_guide_7.jpg) 
<br/><br/>

4b. Eraser: Select the erasure tool from the set of tools in the upper left hand side of screen. Adjust the size of the erasure in the drop down menu on the middle left of the screen. Hold down the pointer and move over the background areas.

 <p align="center">
  <img src="https://github.com/CheethamLab/MyoSAT_ImageJ_Macro/blob/master/Documentation/img/img_mask_guide/icon_eraser.jpg" />
</p>
<br/>

![](Documentation/img/img_mask_guide/mask_guide_8.jpg) 

<br/>
Both tools can be used in conjunction with each other to produce the desired results.
<br/><br/><br/>

![](Documentation/img/img_mask_guide/mask_guide_9.jpg) 
<br/><br/>

5.	When only the area for analysis is left, select the bucket tool from the tool bar on the upper left. Under the ‘Channels’ tab on the middle of the menus on the right, right click on ‘Alpha’ and select ‘Channel to selection’. Under the toolbox on the left side, make sure Foreground is set to white, and background is set to black. Below this, make sure the ‘FG color fill’ and ‘Fill Whole selection’ are checked, under the ‘Bucket Fill’ menu. Click over the image, and it should turn to white. (Notice: If the image doesn’t fill with white likely the right channel wasn’t selected. Try reselecting the alpha channel, or switch to the grey channel and the back to alpha)

<p align="center">
  <img src="https://github.com/CheethamLab/MyoSAT_ImageJ_Macro/blob/master/Documentation/img/img_mask_guide/icon_bucket.jpg" />
</p>
<br/>

 ![](Documentation/img/img_mask_guide/mask_guide_10.jpg) 
 <br/><br/>

6.	Rescale the image back to its original pixel size. Rounding error can result in different sized images, which can cause problems for MyoSAT. It is best to manually enter the original pixel resolution.
<br/>

![](Documentation/img/img_mask_guide/mask_guide_11.jpg) 
<br/><br/>

7.	From the top menus select  ‘Image’ > ‘Flatten Image. This should add solid black to the background. 
<br/>

![](Documentation/img/img_mask_guide/mask_guide_12.jpg) 
<br/><br/>

![](Documentation/img/img_mask_guide/mask_guide_13.jpg) 
 <br/><br/>

8.	Export the image (Top menus: ‘File’ > ‘Export As’). Make sure to save the image as a .tiff file.


