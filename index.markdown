---
#layout: page
layout: home

---

# _privvg_

The [privvg](https://github.com/privvg) project builds tools to generate [differentially-private](https://en.wikipedia.org/wiki/Differential_privacy) synthetic databases from graphical collections of sequence data known as *variation graphs*.
We document our work [here, in a series of blog posts and notes]({{ site.url }}/archives), and [publish our code](https://github.com/privvg) under open source licenses for free use by all.

## variation graphs

A [variation graph](https://ekg.github.io/2019/07/09/Untangling-graphical-pangenomics) represents the mutual alignment of a set of sequences in a compact, visually-accessible structure.
They are used in diverse applications in [genome sequence analysis](https://doi.org/10.1038/nbt.4227), [comparative genomics](https://doi.org/10.1089/cmb.2010.0252), and [linguistics](https://doi.org/10.1016/j.ijhcs.2009.02.001).
A growing community of researchers explores their [applications to pangenomics](https://pangenome.github.io/) and [high-throughput genomics](https://pangenome.github.io/).

The *nodes* of these labeled graphs represent fragments of consecutive sequences (perhaps DNA, protein, text, or locations).
Their *edges* describe allowed or observed transitions between nodes found in actual sequences of interest.
*Paths* record walks of sequences through the nodes of the graph.

![Example variation graph visualization with dot for H-3136]({{ site.url }}/assets/H-3136.dot.png)

## the promise of differential privacy in pangenomics

Human genomes are both useful and difficult to utilize.
Knowing what sequences ([alleles](https://en.wikipedia.org/wiki/Allele) or [haplotypes](https://en.wikipedia.org/wiki/Haplotype)) exist in the population can help us observe and understand new genomes that we assemble.
This is critically useful in fields like medicine, population genetics, and agriculture.
However, it can be [difficult to share genomic information due to issues of privacy](https://doi.org/10.1038/nrg3723).

Researchers have deeply explored techniques to produce [differentially-private summarizations of some genomic information, such as SNPs and other small variants](https://doi.org/10.1038/nrg3723), but thus far no methods approach the question of differential privacy of arbitrary genome sequence and assemblies.
As variation graphs are becoming a standard for the representation of pangenomes, which new sequencing technology is allowing us to rapidly accumulate for [humans](https://humanpangenome.org/) and other species, they are an ideal target for the application of privacy-preserving data release.

## differentially-private mobility data

Location data can be represented in a variation graph by encoding quantized location/times in nodes, and expressing individual movements as paths through these nodes.
Just as a differentially-private variation graph can help us understand common haplotypes tracing through the graph, a differentially-private model of collective mobility information can help us to understand common flows of people through space and time.
These flows are traditionally difficult for researchers and public planners to access and share, due to the risk of identification and tracking of individiuals.
However, in light of the [COVID-19 pandemic](https://en.wikipedia.org/wiki/COVID-19_pandemic) we see critical importance in making them available.
Tools in privvg will support application to mobility data, but work remains to be done to transform the data into 

## our vision

We envision a future in which individuals who assemble their genomes for personal or medical reasons could release (via a trusted third party) useful information from their own genome by mixing their genome and others in a privacy-preserving pangenomic variation graph.
As a synthetic database, this differentially-private variation graph could be used directly as a reference system by tools that work on pangenomes.
This trusted third-party arrangement [matches contemporary practice in genomics](https://gnomad.broadinstitute.org/).
Our implementation simply promises the release of larger-scale information about haplotypic structures and allele frequencies that will become available with ubiquitous genome assembly.

## compact, distributable data models

Methods developed for variation graphs allow the efficient compression of collections of genome and redundant sequence data.
A data structure (using the graph Burrows-Wheeler transform or [GBWT](https://doi.org/10.1093/bioinformatics/btz575)) built from the [1000 Genomes Project](https://www.internationalgenome.org/) sequences can store genomes using only 1 bit per 1000 base-pair of genome sequence.
These approaches are not only effcient, but they are self indexes that support efficient queries to find and match sequences.
Allowing for the redistribution of succinct data structures representing collections of genomes avoids the need to control data access or operate centralized servers.
If they are compact, then researchers will only need minimal resources to use them.

## our funding

[This project is funded](https://nlnet.nl/project/VariationGraph/) through the [NGI0 Discovery Fund](https://nlnet.nl/discovery), a fund established by [NLnet](https://nlnet.nl/) with financial support from the European Commission's [Next Generation Internet](https://ngi.eu/) programme, under the aegis of DG Communications Networks, Content and Technology under grant agreement No 825322.


