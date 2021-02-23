# Using nanopore long-reads to improve the genome assembly for *Ganoderma lucidum* 10597 SS1
**What:** This a repository of a notebook and reports for my *Ganoderma lucidum* 10597 SS1 genome assembly and annotation project. 

**Why:** I have a hypothesis that long-read data can improve the contiguity of the current MycoCosm [genome assembly](https://mycocosm.jgi.doe.gov/Gansp1/Gansp1.home.html) for *Ganoderma lucidum* 10597 SS1 and I wish to hone my bioinformatics skills.

**How:** I generated a small amount of long-read data using a MinION nanopore sequencer and used that data with the attached notebook to produce the attached reports. I will use readily-available tools such as Flye and Pilon to produce a draft de novo assembly as well as LR_Gapcloser to attempt to close gaps in the MycoCosm assembly. I will test genome reconciliation tools and evaluate all assemblies using QUAST and Busco. The graphic in the introduction section outlines my approach.

**Results** I was not able to significantly improve the assembly in my first pass. Using Flye and Pilon with approximately 8x long-reads and the original Illumina short-reads produced by JGI that were available from the SRA as of 02/2021, I was able to produce a draft *de novo* assembly with a Busco correctness score of 94.1%.

**Future Work** I would process the raw traces from the MinION using Bonito and sequence correct using Medaka. I would use the improved long-reads in conjunction with a case-specific parametarization of LR_Gapcloser and the MycoCosm assembly.

## **Introduction**
In addition to their ecological importance and role in the global carbon cycle, wood-degrading fungi (wood-fungi) can be helpful partners for manufacturing bio-based products. In addition to food and medicine, domesticated, non-genetically modified wood-fungi are already helpful partners for creating leather-like materials, plastic foam replacements and a variety of other applications. Synthetic biology for wood-fungi could enable a new class of bio-based products but genetic engineering foundations, such as reference quality annotated genomes and readily available genetic parts, have yet to be realized.

A key component for advanced genetic engineering of any organism is a suitable reference-quality annotated genome assembly. The genome of *Ganoderma lucidum* 10597 SS1 was sequenced, assembled and annotated by the Joint Genome Institute using second generation squencing technology and made publicly available via MycoCosm, but it contains 347 gaps and the 156 scaffolds are not arranged into chromosomes. Gaps in an assembly and lack of registration of scaffolds into chromosomes could hinder genetic engineering efforts by obscuring important sequences for interrogation and limiting assessments of off-target effects of gene editing. Optical mapping technologies could aid in resolving chromosomes but they require additional processing, incurring additional costs. Recently, third-generation long-read sequencing technologies have been used to generate reference-quality annotated genome assemblies for wood-fungi.

Here, I attempted to use a small amount of 

**Approach**

![alt text](/path/img.jpg "Title")
    
## **Results**

## **Future Directions**

## **Methods**

