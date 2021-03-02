# Using nanopore long-reads to improve the genome assembly for *Ganoderma lucidum* 10597 SS1
**What:** This a repository for my *Ganoderma lucidum* 10597 SS1 genome assembly and annotation project. 

**Why:** I have a hypothesis that long-read data can improve the contiguity of the current MycoCosm [genome assembly](https://mycocosm.jgi.doe.gov/Gansp1/Gansp1.home.html) for *Ganoderma lucidum* 10597 SS1 and I wish to hone my genomics skills.

**How:** I generated a small amount of long-read data using a MinION nanopore sequencer and used that data with the attached notebook to produce the attached reports. I used readily-available tools, such as Flye and Pilon, to produce a draft *de novo* assembly as well as LR_Gapcloser to attempt to close gaps in the MycoCosm assembly. I used a genome reconciliation tool and evaluated all assemblies using QUAST and Busco. The graphic in the Methods section outlines my approach.

**Results** I was not able to significantly improve the assembly in my first pass. Using Flye and Pilon with approximately 8x long-reads and the original Illumina short-reads produced by JGI that were available from the SRA as of 02/2021, I was able to produce a draft *de novo* assembly with a Busco correctness score of 94.1%.

**Future Work** I would process the raw traces from the MinION using Bonito to basecall and sequence correct thea new reads using Medaka. I would use the improved long-reads in conjunction with an optimized parametarization of LR_Gapcloser and the MycoCosm assembly, followed by a series of polishing steps using Racon for long-reads and Pilon for short-reads.

## **Introduction**
In addition to their ecological importance and role in the global carbon cycle, wood-degrading fungi (wood-fungi), such as the polypore *Ganoderma lucidum*, can be helpful partners for manufacturing bio-based products. In addition to food and medicine, domesticated, non-genetically modified wood-fungi are already helpful partners for creating leather-like materials, plastic foam packaging replacements and a variety of other applications. Synthetic biology for wood-fungi could enable a new class of bio-based products but genetic engineering foundations, such as reference-quality annotated genomes and readily available genetic parts, have yet to be realized.

A key component for advanced genetic engineering of any organism is a suitable reference-quality annotated genome assembly. The genome of *Ganoderma lucidum* 10597 SS1 was sequenced, assembled and annotated by the Joint Genome Institute using second generation squencing technology and made publicly available via MycoCosm, but it contains 347 gaps and the 156 scaffolds are not arranged into chromosomes. Gaps in an assembly and lack of registration of scaffolds into chromosomes could hinder genetic engineering efforts, such as by obscuring important sequences for interrogation or limiting assessments of off-target effects of gene editing. Optical mapping technologies could aid in resolving chromosomes but they require additional processing, incurring additional costs. Recently, third-generation long-read sequencing technologies, such as Pacific Biosciences HiFi reads, have been used to generate highly contiguous annotated genome assemblies for wood-fungi.

Here, I attempted to use a total of 86385 MinION nanopore long-reads produced by a total of 12 Flongle flow cells and 1 MinION flow cell that were used to sequence the outputs of several gDNA extraction experiments from the same biological sample to improve the contiguity of the MycoCosm genome assembly for 10597 SS1. The total data amounted to 358324061 total bases and a theoretical mean coverage of approximately 8x.

I used several *de novo* assembly tools that are commonly used by the bioinformatics community, such as SPAdes and Flye, as well as newer assemblers, such as HASLR. I also used a gapclosing tool, Long-Read Gapcloser, and a genome reconciliation/merging tool called Quickmerge. Finally, I used QUAST and BUSCO to evaluate select assemblies.
    
## **Results**



## **Future Directions**

I would process the raw traces from the MinION using Bonito to basecall and sequence correct thea new reads using Medaka. I would use the improved long-reads in conjunction with an optimized parametarization of LR_Gapcloser and the MycoCosm assembly, followed by a series of polishing steps using Racon for long-reads and Pilon for short-reads.

## **Methods**
I began by acquiring the Illumina short-reads produced by the JGI. I used SRA-tools to retrieve 3 files from the SRA. I then used the BBMap suite followed by fastp to pre-process the short-reads. I used minimap2 to pre-process the consolidated nanopore reads that were produced by MinKNOW.

Once all the short- and long-reads were pre-processed I executed the processes outlined in the following schematics, using default parameters for all tools with the exception of the number of threads used, where applicable. 

<img src="https://github.com/Rcperez/G-lucidum-hybrid-genome-assembly/blob/main/FlyeAssembly.jpg" width="350" align="left"/>
<img src="https://github.com/Rcperez/G-lucidum-hybrid-genome-assembly/blob/main/HybridAssemblies.jpg" width="350" align="right"/>

Upon completing the above processes I evaluated select assemblies with QUAST, using default parameters and the MycoCosm assembly as the reference assembly.

<p align="center">
  <img src="https://github.com/Rcperez/G-lucidum-hybrid-genome-assembly/blob/main/QUASTevals.jpg" width="400">
</p>

I then evaluated select assemblies using BUSCO. 

<p align="center">
  <img src="https://github.com/Rcperez/G-lucidum-hybrid-genome-assembly/blob/main/BUSCOscores.jpg" width="400">
</p>
