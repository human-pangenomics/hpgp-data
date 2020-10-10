# Human PanGenomics Project

This dataset includes sequencing data, assemblies, and analyses for the offspring of ten parent-offspring trios. 

Data will be added and updated as technologies improve or new data uses are encountered. If you have issues/questions open an issue on this github page.

# Data description

Each parent in the trio was sequenced with <a href="https://www.illumina.com">Illumina</a> short reads, each child was sequenced with <a href="https://www.illumina.com">Illumina</a> short reads, <a href="https://www.10xgenomics.com">10X Genomics</a>, <a href="https://nanoporetech.com">Nanopore</a>, <a href="http://www.pacb.com">PacBio</a> CLR and HiFi (in process), <a href="https://bionanogenomics.com">Bionano</a> and Hi-C.

For nanopore datasets, each folder contains the fast5, fastq (basecalled with Guppy 2.3.5 flip flop with the high accuracy model), and a sequencing summary file.

For PacBio CLR data, each folder contains a subread bam file which can be converted to fasta/q using either ``bam2fastq`` or ``samtools fasta``. The HiFi folders contain ccs.bam files which have already been converted from subreads into high-fidelity reads. As before, they can be converted to fasta/q using `bam2fastq` or ``samtools fasta``.

For Bionano data, each folder contains both the assembled optical map (cmap) and the individual molecules (bnx.gz)

For the remaining short-read data, each folder contains one or more subfolders with fastq.gz files.

# Data download

Data is hosted on AWS with the links below leading to each individual data type. You can download each file directly through the browser or, alternatively, using Amazon's <a href="https://aws.amazon.com/cli/">AWS cli</a>.

For example, to download all PacBio CLR data for HG01109, located at ``https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01109/PacBio_CLR/`` we can remove ``index.html?prefix=`` from the url and replace ``https://s3-us-west-2.amazonaws.com/`` with ``s3://``, giving a URL of ``s3://human-pangenomics/HG01109/PacBio_CLR/``. We can then download all files in this subfolder with the command:
```
aws --no-sign-request s3 sync s3://human-pangenomics/HG01109/PacBio_CLR/ ./
```
To instead download all data for this sample run (NOTE: HiFi and Illumina data will not be downloaded with this command and must be downloaded separately):
```
aws --no-sign-request s3 sync s3://human-pangenomics/HG01109/ ./
```

There are many other s3 commands, such as ls and cp to list folder contents or to download individual files. Check the AWS documentation for more information. Amending the `max_concurrent_requests` etc. settings as per <a href="https://docs.aws.amazon.com/cli/latest/topic/s3-config.html">this guide</a> will improve download performance further.

Below are the links to download each datatype:

* HG01109 (Male, PUR)
   - Father HG01107 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01107/illumina/">data</a>
   - Mother HG01108 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01108/illumina/">data</a>
   - Illumina <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/002/ERR3988842/ERR3988842_1.fastq.gz">left</a> and <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/002/ERR3988842/ERR3988842_2.fastq.gz">right</a> pairs
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01109/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01109/PacBio_CLR/">data</a>
   - PacBio HiFi <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=submissions/8fa7bde9-be6f-4160-97a9-b639a8962c66--WUSTL_OTHER_HiFi/HG01109/PacBio_HiFi/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01109/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01109/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01109/hic/">data</a>

* HG01243 (Male, PUR)
   - Father HG01241 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01241/illumina/">data</a>
   - Mother HG01242 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01242/illumina/">data</a>
   - Illumina <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/008/ERR3988858/ERR3988858_1.fastq.gz">left</a> and <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/008/ERR3988858/ERR3988858_2.fastq.gz">right</a> pairs
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01243/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01243/PacBio_CLR/">data</a>
   - PacBio HiFi <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=submissions/8fa7bde9-be6f-4160-97a9-b639a8962c66--WUSTL_OTHER_HiFi/HG01243/PacBio_HiFi/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01243/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01243/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01243/hic/">data</a>

* HG02080 (Female, KHV)
   - Father HG02082 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02082/illumina/">data</a>
   - Mother HG02081 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02081/illumina/">data</a>
   - Illumina <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/006/ERR3988986/ERR3988986_1.fastq.gz">left</a> and <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/006/ERR3988986/ERR3988986_2.fastq.gz">right</a> pairs
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02080/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02080/PacBio_CLR/">data</a>
   - PacBio HiFi <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=submissions/8fa7bde9-be6f-4160-97a9-b639a8962c66--WUSTL_OTHER_HiFi/HG02080/PacBio_HiFi/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02080/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02080/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02080/hic/">data</a>

* HG03098 (Male, MSL)
   - Father HG03096 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03096/illumina/">data</a>
   - Mother HG03097 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03097/illumina/">data</a>
   - Illumina <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/009/ERR3989119/ERR3989119_1.fastq.gz">left</a> and <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/009/ERR3989119/ERR3989119_2.fastq.gz">right</a> pairs
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03098/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03098/PacBio_CLR/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03098/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03098/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03098/hic/">data</a>

* HG02055 (Male, ACB)
   - Father HG02053 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02053/illumina/">data</a>
   - Mother HG02054 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02054/illumina/">data</a>
   - Illumina <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/009/ERR3988979/ERR3988979_1.fastq.gz">left</a> and <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/009/ERR3988979/ERR3988979_2.fastq.gz">right</a> pairs
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02055/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02055/PacBio_CLR/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02055/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02055/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02055/hic/">data</a>

* HG03492 (Male, PJL)
   - Father HG03490 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03490/illumina/">data</a>
   - Mother HG03491 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03491/illumina/">data</a>
   - Illumina <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/003/ERR3989173/ERR3989173_1.fastq.gz">left</a> and <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/003/ERR3989173/ERR3989173_2.fastq.gz">right</a> pairs
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03492/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03492/PacBio_CLR/">data</a>
   - PacBio HiFi <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=submissions/8fa7bde9-be6f-4160-97a9-b639a8962c66--WUSTL_OTHER_HiFi/HG03492/PacBio_HiFi/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03492/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03492/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG03492/hic/">data</a>

* HG02723 (Female, GWD)
   - Father HG02721 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02721/illumina/">data</a>
   - Mother HG02722 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02722/illumina/">data</a>
   - Illumina <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/000/ERR3989060/ERR3989060_1.fastq.gz">left</a> and <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/000/ERR3989060/ERR3989060_2.fastq.gz">right</a> pairs
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02723/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02723/PacBio_CLR/">data</a>
   - PacBio HiFi <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=submissions/8fa7bde9-be6f-4160-97a9-b639a8962c66--WUSTL_OTHER_HiFi/HG02723/PacBio_HiFi/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02723/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02723/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02723/hic/">data</a>

* HG02109 (Female, ACB)
   - Father HG02107 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02107/illumina/">data</a>
   - Mother HG02108 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02108/illumina/">data</a>
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02109/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02109/PacBio_CLR/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02109/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02109/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02109/hic/">data</a>

* HG01442 (Male, CLM)
   - Father HG01440 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01440/illumina/">data</a>
   - Mother HG01441 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01441/illumina/">data</a>
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01442/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01442/PacBio_CLR/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01442/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01442/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG01442/hic/">data</a>

* HG02145 (Male, ACB)
   - Father HG02143 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02143/illumina/">data</a>
   - Mother HG02144 Illumina <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02144/illumina/">data</a>
   - Illumina <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/005/ERR3988995/ERR3988995_1.fastq.gz">left</a> and <a href="http://ftp.sra.ebi.ac.uk/vol1/fastq/ERR398/005/ERR3988995/ERR3988995_2.fastq.gz">right</a> pairs
   - 10XG <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02145/10X/">data</a>
   - PacBio CLR <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02145/PacBio_CLR/">data</a>
   - Nanopore <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02145/nanopore/">data</a>
   - Bionano <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02145/BioNano/">data</a>
   - Hi-C <a href="https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=HG02145/hic/">data</a>

