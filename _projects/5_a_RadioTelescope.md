---
layout: page
title: Amateur Radio Telescope
description: Team Lead
img: assets/img/5_a_RadioTelescope/cover.jpeg
importance: 5
category: academic
related_publications: false
---

{% include figure.liquid loading="eager" path="assets/img/5_a_RadioTelescope/cover-2.jpeg" title="Final showcase!" class="img-fluid rounded z-depth-1" %}

### Introduction

My team set out to build an amateur radio telescope horn antenna using easily available materials and RF equipment, that can detect neutral hydrogen radio emissions at 1420.4MHz, and perform digital signal processing using existing GNUradio scripts.

We decided to build this project as part of our Electromagnetics & Applications course as it was:

- Easy to build, relatively cheap 
    - Hydrogen line systems offer a low barrier of entry
- Educational! Provides educational opportunities in:
    - Radio astronomy and astrophysics fundamentals
    - Antenna design and fabrication
    - RF front end design
    - Lots of further development pathways to larger and more sensitive equipment (e.g. larger antenna, more sensitive electronics, dual antenna interferometry)


### Simulation and Analysis

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5_a_RadioTelescope/analysis-1.jpg" title="Farfield 3D" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
            Figure 1: Farfield 3D plot
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5_a_RadioTelescope/analysis-2.png" title="Farfield 2D" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
            Figure 2: Farfield 2D plot
        </div>
    </div>
</div>

The horn antenna is simulated in CST Suite to validate its performance. Unfortunately, we were not able to obtain a satisfactory S11 (return loss) parameter due to inadequate experience with simulating very large antennas in CST.  

### Results

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5_a_RadioTelescope/firstlight.png" title="Issue with frequency offset" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
            Figure 3: First light observation after plotting on Excel
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5_a_RadioTelescope/firstlight.jpeg" title="RF Design (old vs new)" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
            Figure 4: Physical setup for observation
        </div>
    </div>
</div>

The first light of the instrument was achieved on 1st August 2024, with the DSPIRA Spectrometer program running on GNURadio. 

#### What did we do well?

- **Antenna** fabrication: 
    - The antenna was physically more robust compared to the original DSPIRA antenna. 
    - More suited to mass production due to ease of manufacture for professional metalworking shops
- **1st Stage RF** design: a good first stage design gives good leeway for future expansion

#### What could have been done better?

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5_a_RadioTelescope/signal-problem.png" title="Issue with frequency offset" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
            Figure 5: Frequency peak at 1420.3MHz instead of the expected 1420.4MHz
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5_a_RadioTelescope/rf-design.png" title="RF Design (old vs new)" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
            Figure 6: Original RF design (top) and the current RF design (bottom)
        </div>
    </div>
</div>

- The **software defined radio**
    - The clone HackRF One SDR has significant spurious signals due to shoddy workmanship (possibly inadequate EMI mitigation) and component quality
    - Significant frequency shift of -0.1MHz 
    - Consider external high accuracy clock source to allow for accurate quantitative measurements (e.g. Doppler)
- **Better RF design** in 2nd stage
    - Since we accidentally burnt one LNA...the current setup is not ideal
    - Take advantage of LNAs that accept a DC bias voltage to reduce cabling


### Further readings

This project was also presented at the Singapore Amateur Radio Transmitting Society (SARTS) quarterly meetup [here](https://www.sarts.org.sg/amateur-radio-astronomy/). 

For further resources should you wish to learn more about amateur radio astronomy and the resources that helped us build this project, please review [this document](https://docs.google.com/document/d/1Pru6DykEi6ew-fNuoGPplmVMCXZPy2PJq5DlZFhtc58/edit?usp=sharing).
