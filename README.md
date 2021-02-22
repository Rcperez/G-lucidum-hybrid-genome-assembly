# Using nanopore long-reads to improve the genome assembly for *Ganoderma lucidum* 10597-SS1
**What:** This a repository of a notebook and reports for my *Ganoderma lucidum* 10597-SS1 genome assembly and annotation project. 

**Why:** I have a hypothesis that long-read data can improve the contiguity of the current MycoCosm [genome assembly](https://mycocosm.jgi.doe.gov/Gansp1/Gansp1.home.html) for *Ganoderma lucidum* 10597-SS1 and I wish to practice my bioinformatics skills.

**How:** I generated a small amount of long-read data using a MinION nanopore sequencer and used that data with the attached notebook to produce the attached reports. I will use readily-available tools such as Flye and Pilon to produce a draft de novo assembly as well as LR_Gapcloser to attempt to close gaps in the MycoCosm assembly. I will test genome reconciliation tools and evaluate all assemblies using QUAST and Busco. The graphic in the introduction section outlines my approach.

**Results** I was not able to significantly improve the assembly in my first pass. Using Flye and Pilon with approximately 8x long-reads and the original Illumina short-reads produced by JGI that were available from the SRA as of 02/2021, I was able to produce a draft *de novo* assembly with a Busco correctness score of 94.1%.

## **Introduction**

**Approach**

![alt text](/path/img.jpg "Title")
    
## **Results**

## **Future Directions**

## **Methods**

