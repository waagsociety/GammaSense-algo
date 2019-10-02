# Gammasense-algo
Algorithm to extract gamma rays CMP from CMOS camera reading.
The project has been a collaboration between [Waag](https://waag.org), [WISE Nederland](https://wisenederland.nl/) with the support of [SIDN fonds](https://www.sidnfonds.nl/).

# CMOS research
## What did we try to achieve?
Since some years it has been known that ionizing radiations such as alpha,beta and gamma rays can interact with the CMOS layer present in smartphone and webcam. This interaction is detected by the camera as a lit pixel, representing the point where the ray hits the CMOS layer and causes an electric discharge, which is recorded by the camera. This mechanism is analogous to a light ray interaction, and therefore to detect radiations we need to isolate their effect from the effect of light. This can be done by exploiting the property of gamma rays to easily go through several materials. Some layers of tape on a CMOS camera can stop light and let the gamma rays go through.

These facts together make out of every smartphone a potential gamma ray detector. This was the context in which our activities to study whether it was possible to use smartphone CMOS camera as a Citizen Sensing tool for measuring radiation.

## What activities did we do?
We wanted to test whether we could measure radiation with a smartphone or computer camera. To do so we developed a script embedded in a web page, which, once loaded in a browser, accessed the data of the (taped-off) camera, and recorded them on a file each minute. The data was effectively black pictures with some white spots, representing gamma ray hits. We went in a lab at RIVM where we tried to measure radioactive sources contemporarily with our devices and with professional equipment. The idea was to compare our results to the "ground truth" provided by the professional equipment, and try to develop an algorithm that would transform the pictures taken by the camera in number of radiation hits per minute (count per minute or CPM).
## What results did we reach?
We set up a data analysis platform where we tested several solutions. This was done in R and we used algorithms from literature, most notably the high-delta algorithm.
## What issues/problems did we face?
Because of the nature of consumer electronics, most of the lit pixels in a picture are not due to gamma rays, but to electronic noise. The main issue is therefore to distinguish whether a lit pixel (a value different from zero in the camera matrix) is due to noise or to a gamma ray. We tried to use some threshold to separate noise from real radiation, but we were not always able to replicate the measurements of the professional equipment. In some cases we could see a signal above the noise when we knew that a radiation source was used, but in other cases it was not possible to consistently separate the noise from the signal.
This is particularly impacting considering the fact that the radiation source used during the lab tests are many times stronger than normal levels of radiation present in nature, and a measurement device should definitely be able to detect them.
## How can (we) move forward with this research?
Due to lack of time we could not investigate further these issues, also due to the fact that to conduct an experiment one needs to have radioactive sources, and these are not easy to obtain. We acquired an exemplar of Uranium glass, but this is only slightly radioactive and much weaker than a lab source.
We still believe that there is some potential in this direction, especially when combined with the fact that due to the widespread presence of smartphones, many measurements could be obtained of a particular area, therefore potentially complementing the limitations of a single device with the abundance of devices and measurements.
Such a believe is funded in the results that have been obtained in literature with CMOS cameras, so there is definitely potential in this direction.

## References
Whiteson, Daniel, Michael Mulhearn, Chase Shimmin, Kyle Cranmer, Kyle Brodie, and Dustin Burns. 2016. “Observing Ultra-High Energy Cosmic Rays with Smartphones.” Astroparticle Physics 79 (June): 1–9. https://doi.org/10.1016/j.astropartphys.2016.02.002.

Tith, Sandy, and Nares Chankow. 2016. “Measurement of Gamma-Rays Using Smartphones.” Open Journal of Applied Sciences 6 (6): 31–37. https://doi.org/10.4236/ojapps.2016.61004.

Geijter, Laura De. 2015. “Gammastraling Meten Met Smartphones.” Saxion Hogeschool.

Cogliati, Joshua J., Kurt W Derr, and Jayson Wharton. 2014. “Using CMOS Sensors in a Cellphone for Gamma Detection and Classification.” ArXiv Preprint ArXiv:1401 .0766v1, 1–26. http://arxiv.org/abs/1401.0766.

Wagner, Eric, Rich Sorom, and Linda Wiles. 2016. “Radiation Monitoring for the Masses.” Health Physics 110 (1): 37–44. https://doi.org/10.1097/HP.0000000000000407.
