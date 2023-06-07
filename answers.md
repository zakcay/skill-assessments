Q1) How many positions are found in this region in the VCF file?

A: 105 positions

Command: bcftools view -r 1:1105411-44137860 CEU.exon.2010\_03.genotypes.vcf.gz | wc -l

Q2: How many samples are included in the VCF file?

A: 90 samples

Command: bcftools query -l CEU.exon.2010\_03.genotypes.vcf.gz | wc -l


Q3: How many positions are there total in the VCF file?

A: 3489 positions

Command: bcftools query -f '%POS\n' CEU.exon.2010\_03.genotypes.vcf.gz | wc -l


Q4: How many positions are there with AC=1? Note that you cannot simply count lines since the output of bcftools filter includes the VCF header lines. You will need to use bcftools query to get this number.

A: 1075 positions (number of records)

Command: bcftools filter -i AC=1 CEU.exon.2010\_03.genotypes.vcf.gz | bcftools stats

Q5: What is the ratio of transitions to transversions (ts/tv) in this file?

A: 3.47

Command: bcftools stats  CEU.exon.2010\_03.genotypes.vcf.gz

Rewrite chromosomes with prefix chr:

Command: bcftools annotate CEU.exon.2010\_03.genotypes.vcf.gz --rename-chrs chr\_name\_conv.txt -Oz -o CEU.exon.2010\_03.genotypes.chr\_conv.vcf.gz

Q6: What is the median number of variants per sample in this data set?

A: 55.427 (Total number of variants/number of samples)
