## Challenge 1: Variant calling in an Anopheles Gambaie cross

### Introduction

This challenge is to create as accurate a call set as possible for an experimental cross of the major malaria vector _Anopheles gambiae_.
The father of the cross is from a highly inbred colony from Kisumu, Kenya- first put into colony in the 1970s. 
As a result we expect the father to be highly homozygous.
The mother is from a much more recently colonised line (Ghana) and therefore expected to have substantially higher levels of variation. 

### Samples

Samples are 22 whole genome sequences from an experimental cross. Included in the set are the 2 parents and 20 progeny.
`samples.csv` describes the sample ID, the ENA accession IDs, and the role (mother/father/progeny) of each sample.
Data are provided as `bam` files for convenience, but we anticipate most groups will wish to perform realignment and recalibration.

Samples were sequenced using an Illumina Hi-seq. All samples have a median coverage of at least 16x.

### Rules

Produce a set of variant calls against the AgamP4 reference genome available from [Vectorbase](https://www.vectorbase.org/downloadinfo/anopheles-gambiae-pestchromosomesagamp4fagz).
Both SNPs and indels should be called.
Calls against chromosomes 2R and 3R should be submitted for evaluation as detailed below.
It is permitted to use pedigree information to calibrate models against chromosomes 2L, 3L and X.
However the submitted calls should not leverage pedigree information.

### Evaluation

Callsets will be explored to identify consistent causes of error, to assist algorithmic improvement.
The precise method of evaluation will not be published until entries for this challenge are complete. 
Although it will be based on mendelian consistency and parsimony of inheritance.

### Submission

Submissions are made by submitting a pull request against the master branch of this repository.
A new directory should be made in the submissions subdirectory, following the convention {tool}-{institution}: for example unifiedgenotyper-bdioxford.
The folder must contain a metadata file called `submission.yml`, containing the following keys.

 - title: Title of the approach, perhaps a tool and version number.
 - institution: Short name of submitting institution
 - file: Path to a hosted multisample VCF 4.2 file or gVCF file.
 - submitter: Name and email address of submitter
 - contributors: Name and email address of contributors
 - code: (url to code used to generate results). Ideally a github commit of a pipeline specification with environment definitions.
 - method: A brief description of the method/approach.
 - notes: Any other pertinent information
