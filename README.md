<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#Intruduction">Getting Started</a></li>
    <li><a href="#final parameters">Usage</a></li>
    <li><a href="#block diagram">Roadmap</a></li>
    <li><a href="#PCB design">Contributing</a></li>
    <li><a href="#Cover design">License</a></li>
    <li><a href="#Measurements">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

![done](https://github.com/user-attachments/assets/41e997ae-4e98-4cf5-ba99-e6846f72921f)

My design of an RF generator based on the ADF4350, used as a heterodyne signal in my radiotelescope.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Introduction

The assumption of the project was to create a small and simple RF generator, with good parameters and high stability. At the very beginning, the generator design based on separate components was eliminated, i.e. separate VCO, PLL, dividers, multiplexers and final stages. Such a design can provide the best stability and noise parameters and be freely and easily modified, but it requires complex design and time-consuming tests. In this straightforward project, reliance is placed on the use of a Wideband Synthesizer with Integrated VCO, which will provide good parameters and in one "silicon" unit will have integrated basic components of the RF generator and the ability to program the output frequencies. I decided on the ADF4350 because of the parameters that were in line with the assumptions. What's more, the free samples I received from the manufacturer were an additional advantage.

## Final parameters

•	Dimensions: 
PCB: 51mm x 46mm, 
Cover:  58mm x 53mm x 27mm
•	Power supply: +5V, >200mA
•	Output power: 9-15dBm
•	Frequency range: 550-4400MHz
•	4 programmable frequency values
•	SMA connectors
•	Frequency stability: +/- 350 Hz (depends on the frequency)
•	Phase noice: (-85) – (-105) dBc/Hz
•	Harmonics: -4dB (worst case)

## Block diagram

![Adf4350_RF_gen drawio](https://github.com/user-attachments/assets/f219a649-256a-4758-9969-46e661803fcd)

## PCB design

![layers](https://github.com/user-attachments/assets/94284aad-47f5-4887-89cc-dd1d61b8e70b)

To maintain the intended dimensions and improve RF properties (thinner 50 Ohm paths), the PCB is 4-layer.
The design was based on a schematic diagram provided by the manufacturer in the catalog note. To ensure high stability, each voltage pin has its own stabilizer and copper plates. The mass is common, only under the quartz it is cut off. For easier assembly (soldering the ground pad), there is an enlarged hole in the PCB. The mounting holes were placed in convenient places due to the planned use of a 3D printed casing, designed for PCB. An exposed copper ring is used to mount the RF shielding.

## Cover design

![rend](https://github.com/user-attachments/assets/368149ce-528a-4097-9044-21cd6d2c8bd4)

The case was designed in Fusion360 using a PCB model generated in KiCad. 2 screws were used to screw the PCB to the lower part of the cover, another two were used to connect both parts of the case. There are also holes for 2 LEDs, a DC power and SMA connectors. To improve the appearance, the outer layers of the housing were printed using the Hilbert curve on an Ender 3 printer.

## Measurements

Measurements were made according to the connections shown in the diagram below. For this purpose, a Rohde&Schwarz FSV spectrum analyzer and a pendulum frequency counter, model CNT-104S, were used. The generator was powered by a laboratory power supply. All devices were turned on for at least 1 hour before the measurement to stabilize the temperature and achieve stable measurement conditions. The frequency stability measurement took 4 hours, after which the generator was switched to the input of the spectrum analyzer and after waiting 30 minutes, measurements of harmonics, signal power and phase noise were made. The procedure was repeated for 3 frequencies from different operating ranges of the ADF4350 synthesizer: 600MHz, 1380MHz and 2400MHz.

![uklad_pomiarowy drawio](https://github.com/user-attachments/assets/cabe9ea6-f346-4bdc-83a6-e435a6b4c6d0)

Measurement results for the 600MHz frequency:
•	Output frequency (exact): 600001200 Hz
•	Frequency stability: +/-150Hz
•	Power consumption: 0,79mW
•	Output power: 14,34 dBm
•	Phase noice (10kHz): -103,1dBc/Hz
•	Harmonics: 2nd: -9dB, 3rd: -20dB, 4th: -25dB

![600MHz](https://github.com/user-attachments/assets/d889a8a8-285c-4e35-8fce-2a8144298d5f)

Measurement results for the 1380MHz frequency:
•	Output frequency (exact): 1380002470 Hz
•	Frequency stability: +/-300 Hz
•	Power consumption: 0,73 mW
•	Output power: 9,1 dBm
•	Phase noice (10 kHz): -90,25 dBc/Hz
•	Harmonics: 2nd: -16dB, 3rd: -4dB, 4th: -25dB

![1380MHz](https://github.com/user-attachments/assets/35dca320-ed16-426d-aaf7-635185f00db0)

Measurement results for the 2400MHz frequency:
•	Output frequency (exact): 2400004910 Hz
•	Frequency stability: +/-350Hz
•	Power consumption: 0,72 mW 
•	Output power: 11,45 dBm
•	Phase noice (10kHz): -87,57 dBc/Hz
•	Harmonics: 2nd: -15dB, 3rd: out of range FSV

![2400MHz](https://github.com/user-attachments/assets/e77ad9fe-5c1d-4430-828d-54eb03122ea4)
