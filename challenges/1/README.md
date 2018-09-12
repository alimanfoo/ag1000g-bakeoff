## Challenge 1: Variant calling in an Anopheles Gambaie cross

### Introduction



### Samples

Samples are 22 whole genome sequences from an experimental cross. Included in the set are the 2 parents and 20 progeny.
`samples.csv` describes the sample Id, the ENA accession IDs, and the role (mother/father/progeny) of each sample.

Samples were sequenced in 20?? on an Illumina high seq. All sample have a median coverage of at least ??x.


### Rules

Produce a set of variant calls against the AgamP4 reference genome available from Vectorbase. (link)
Both SNPs and indels should be called.
Calls against chromosomes 2R and 3R should be submitted for evaluation as detailed below.
It is permitted to use pedigree information to calibrate models against chromosomes 2L, 3L and X.
However the submitted calls should not leverage pedigree information.


### Evaluation

The precise method of evaluation will not be published until entries for this challenge are complete. 
However, it will be based on mendelian consistency and parsimonius inheritance.

### Submission

Submissions are made by submitting a pull request against the master branch of this repository.
A new directory should be made in the submissions subdirectory, following the convention {tool}-{institution}: for example unifiedgenotyper-bdioxford.
The folder must contain a metadata file called `submission.yml`, containing the following keys.

 - title: Title of the approach, perhaps a tool and version number.
 - institution: 
 - file: Path to a hosted VCF file or gVCF file.
 - submitter
 - contributors
 - code
