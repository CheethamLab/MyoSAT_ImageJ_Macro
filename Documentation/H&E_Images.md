### Using H&E Images with MyoSAT 
___

In addition to collagen V labeled IHC, MyoSAT can be used to analyze muscle cross-sections stained with hematoxylin and eosin. Select the checkbox for 'H&E stained image' on the main settings page, to run a color deconvolution extracting the eosing stain and convert to grayscale. Results will be best for images with evenly stained cytoplasm and clearly separated myofibers. The image below provides an example that can be processed using default parameters for MyoSAT.

<img src="img/Tutorial_H&E_settings_1.tif" alt="H&E_settings_1"
	title="H&E checkbox" width="661" height="250" />
<br>
> **Test Image Filename:**   Strange_2014_4a_low_res.jpg <br>
> **Image Size:**            423x330 pixels  <br>
> **Image Scale:**           2.778 µm/pixel  <br>
> **Format:**                16Bit Grayscale TIFF <br> 
>![](img/Strange_2014_4a_low_res.jpg)
>![](img/Strange_2014_4a_low_res_SEGMENTATION_RESULT.jpg)
>![](img/Strange_2014_4a_low_res_SEGMENTED_IMAGE.jpg)
><img src="img/Strange_2014_4a_low_res_FIBER_DIAMETERS.jpg" alt="Strange_2014"
	title="Strange_2014" width="423" height="330" />

<br>

Images with less even staining, artifacts in the cytoplasm, or higher resolutions may need parameters adjusted to prevent areas of white inside the myofiber from being detected as lines outside the fibers.
The image below is the same as the first image, but at a higher resolution. Processing it with the default parameters will give poor results as irregularities on the left of the image are detected as lines.

> **Test Image Filename:**   Strange_2014_4a_high_res.jpg <br>
> **Image Size:**            1152x908 pixels  <br>
> **Image Scale:**           1.033 µm/pixel  <br>
> **Format:**                16Bit Grayscale TIFF <br> 
><img src="img/Strange_2014_4a_high_res.jpg" alt="Strange_2014"
	title="Strange_2014" width="423" height="330" />
><img src="img/Strange_2014_4a_high_res_SEGMENTATION_RESULT.jpg" alt="Strange_2014"
	title="Strange_2014" width="423" height="330" />
><img src="img/Strange_2014_4a_high_res_SEGMENTED_IMAGE.jpg" alt="Strange_2014"
	title="Strange_2014" width="423" height="330" />	
><img src="img/Strange_2014_4a_high_res_FIBER_DIAMETERS.jpg" alt="Strange_2014"
	title="Strange_2014" width="423" height="330" />

To reduce noise the 'median filter kernal size' and the 'anisotropic diffusion sigma' can be adjusted. The 'ridge detect line width' and contrast levels can also be adjusted to be more selective for the lines outside the fibers.
To experimentally determine these parameters, select 'RUN [Config Settings (Advanced)]' from 'COMMAND' drop down menu.

<img src="img/Tutorial_H&E_settings_2.tif" alt="H&E_settings1"
	title="H&E checkbox" width="661" height="250" />

This provides a preview of key steps in the process, where parameters of the median filter, anisotropic diffusion filter, and ridge detection can be adjusted before moving to the next step. For each step change mode to 'SET' when the desired parameter has been found. Once a suitable set of parameters have been found, they can be used on sets of similar images. 


For the above image, improved results were found using:

**Median Filter Kernal:** 60 µm <br>
**Anisotropic Diffusion Sigma:** 10 µm <br>
**Ridge Detection Line Width:** 15 µm <br>
**Ridge Detect Low Contrast:** 20 <br>

All other parameters set to defaults.

References: <br>
Raw images courtesy of:
Strange, H., Scott, I. & Zwiggelaar, R. Myofibre segmentation in H&E stained adult skeletal muscle images using coherence-enhancing diffusion filtering. BMC Med Imaging 14, 38 (2014). https://doi.org/10.1186/1471-2342-14-38
