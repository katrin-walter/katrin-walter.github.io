---
layout: page
title: WGS-Analysis-Pipeline
description: End-to-end WGS pipeline from raw reads to variant detection.
img: assets/img/ChatGPT Image 2. Mai 2026, 10_04_27.jpg
importance: 3
category: work
---

### Project context
Whole genome sequencing of green algae (Chlorophyta), with the goal of expanding a sparse reference database and identifying polymorphisms and heteroplasmy. The dataset combined Nanopore long reads with Illumina short reads, allowing a hybrid approach. Detailed code and results are kept private until publication.

### Strategy
Working with a non-model organism and limited reference material meant that standard pipelines did not apply out of the box. Each step required testing tools, comparing outputs, and adapting the workflow to the specific data type, whether organellar, nuclear, or microbial. The pipeline below reflects the path that worked, after several that did not.

### Pipeline overview

    Quality cotrol. 
    Nanopore reads were filtered with NanoStat and NanoFilt, Illumina reads trimmed with Trimmomatic.
    A k-mer distribution check gave a first sense of genome size and contamination.

...

    Read filtering by component. 
    Organellar, nuclear, and microbial fractions were separated before assembly. 
    Mapping against curated NCBI references with Minimap2 and Samtools formed the backbone, 
    supported by KAT for eukaryotic filtering and the Metagenome-Atlas pipeline for the microbial fraction.

...

    Assembly and polishing. 
    Canu or SPAdes were used depending on the component, with hybrid input where applicable. 
    Nanopore-based assemblies were polished and reviewed in IGV alongside k-mer plots.

...

    Assembly quality assessment. 
    Completeness was checked with BUSCO against the matching lineage dataset before moving on.

...

    Annotation. 
    Features were annotated with GeSeq, BLAST, ARAGORN, tRNAscan-SE, and ORFfinder. 
    OGDraw visualized the organellar genome.

...

    Variant calling. BAM files from Samtools were passed into SNAPE-pooled, a Bayesian caller built for 
    pooled data. Called variants were cross checked in IGV to verify read-level support and rule out 
    mapping artefacts.

### Tech stack
Bash · Python · executed on an HPC environment


### What this project taught me
The hardest part was not running the tools, but choosing the right one for each step and recognizing when something was not adding up. Each setback pushed me to step back, try alternatives, and document what worked. Looking back, patience and persistence carried this project as much as the tools themselves.

    
    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
