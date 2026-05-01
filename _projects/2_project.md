---
layout: page
title: wet lab 16S rRNA Pipeline
description: End-to-end 16S rRNA Nanopore workflow from sample to sequencing data.
img: assets/img/Gemini_Generated_Image_vxbcq9vxbcq9vxbc Kopie2.jpg
importance: 2
category: work
giscus_comments: false
---

### Goal
Profiling the host-associated microbiomes of marine organisms (green, red and brown macroalgae, seagrasses, mangroves) and sediment to identify the bacterial taxa that drive host growth and survival. Such "key taxa" are directly relevant for biotech applications and cultivation, where defined microbial communities can stabilise yields and improve the success of host organisms in controlled settings.


### Wet lab
Bead-based homogenisation followed by DNA extraction with the Zymo Quick-DNA kit, selected for the most time-efficient handling of large sample numbers. 16S amplification (PCR) and barcoding flowed directly into the Oxford Nanopore library preparation. In parallel, swab samples from selected hosts were used to isolate single bacterial colonies, which were amplified directly from picked colonies and sequenced by Sanger to confirm specific taxa at high resolution.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/IMG_4640.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/IMG_5873.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/IMG_6671.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Working under sterile conditions in the laminar flow hood. Bacterial isolates in liquid media and bacterial colonies on agar plates, ready for picking and single-colony isolation.
</div>

### Sequencing
16S rRNA amplicons were barcoded and prepared for sequencing following the Oxford Nanopore protocol, then sequenced on the MinION using Flongle flow cells with 12 multiplexed samples per run. Sanger sequencing of single colonies was used as a complementary, high-confidence reference for individual isolates.

### Outcome
A reproducible wet-lab workflow for long-read microbiome profiling that scales from whole environmental samples to single bacterial colonies. The workflow delivers sequencing-ready data for identifying the bacterial taxa most relevant to host growth and survival — directly applicable to biotech production, aquaculture, and controlled cultivation. Downstream bioinformatic analysis is described in the dry-lab project.

<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Bildschirmfoto 2023-11-27 um 18.47.37.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/IMG_5616.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    16S rRNA amplicons, multiplexed and sequenced for 24 hours on the Oxford Nanopore MinION with Flongle flow cells (12 samples per run).
</div>

### Stack
Oxford Nanopore (MinION, Flongle) · Sanger sequencing · 16S rRNA amplicon PCR · Zymo Quick-DNA extraction · multiplexed library preparation
