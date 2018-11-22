## Challenge 1: SNP and indel variant calling in an _Anopheles gambiae_ cross

### Introduction

This challenge is to create as accurate a call set as possible for an experimental cross of the major malaria vector _Anopheles gambiae_.
The father of the cross is from a highly inbred colony from Kisumu, Kenya- first put into colony in the 1970s. 
As a result we expect the father to be highly homozygous.
The mother is from a much more recently colonised line (Ghana) and therefore expected to have substantially higher levels of heterozygosity. 

### Samples

Samples are 22 whole genome sequences from an experimental cross. Included in the set are the 2 parents and 20 progeny.
[samples.csv](samples.csv) describes the sample ID, the ENA accession IDs, and the role (mother/father/progeny) of each sample.
Data are provided as `bam` files for convenience, but we anticipate most groups will wish to perform realignment and recalibration.

Samples were sequenced using an Illumina HiSeq. All samples have a median coverage of at least 16x.

### Rules

Produce a set of variant calls against the AgamP4 reference genome available from [Vectorbase](https://www.vectorbase.org/downloadinfo/anopheles-gambiae-pestchromosomesagamp4fagz).
Both SNPs and indels can be called, although submissions with SNPs or indels only are also welcome.
Calls against chromosomes 2R and 3R should be submitted for evaluation as detailed below.
It is permitted to use pedigree information to calibrate models against chromosomes 2L, 3L and X.
However the submitted calls should not leverage pedigree information.

### Evaluation

Callsets will be explored to identify consistent causes of error, to assist algorithmic improvement.
The precise method of evaluation has not yet been finalised, and we welcome comments and discussion via [this issue](https://github.com/malariagen/ag1000g-bakeoff/issues/5). 
Evaluation will be based on Mendelian consistency and parsimony of inheritance.

### Submission

Submissions are made by submitting a pull request against the master branch of this repository.
A new directory should be made in the submissions subdirectory, following the convention {tool}-{institution}: for example "unifiedgenotyper-bdioxford".
The folder must contain a metadata file called `submission.yml`, containing the following keys.

 - title: Title of the approach, perhaps a tool and version number.
 - institution: Short name of submitting institution
 - file: Path to a hosted multi-sample VCF 4.2 file, containing variant calls for all individuals within the cross.
 - submitter: Name and email address of submitter
 - contributors: Name and email address of contributors
 - code: (url to code used to generate results). Ideally a github commit of a pipeline specification with environment definitions.
 - method: A brief description of the method/approach.
 - notes: Any other pertinent information
