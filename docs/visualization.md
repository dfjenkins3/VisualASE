# Gene Visualization 

## What is it?

The visualization can be used to explore the allele expression pattern across a 
gene of interest. It displays the frequency of the alternate allele for all 
SNPs across the gene of interest that are heterozygous in at least one of the 
samples in the data set. It is a useful way to determine the confidence for a 
particular allele specific expression call, and if the ASE is occurring across 
the entire gene or in a subset of the genes.

## The Search Bar

Use the search bar to search for a particular gene of interest. The search is 
not case sensitive. Type your gene of interest into the bar and click the 
submit button.  If the gene you entered exists in the database, the 
visualization will display below the search bar.

## The Gene Visualization

### Gene Name and Strand

The first result will be the name of the gene currently visualized and the 
strand of the reference genome on which the gene is located.  If the strand is 
positive ('+'), the gene visualizations will be displayed from left to right 
in 5' to 3' orientation with the 5' UTR on the left.  If the strand is negative 
('-'), the gene will be displayed from left to right in 3' to 5' orientation 
with the 5' UTR on the right.  

### Coordinates

Below the name and strand of the gene are the chromosomal coordinates of the 
currently displayed gene.  These coordinates are based on the human reference 
genome, version hg38, and can be used in a variety of other databases and 
websites to get more information about the gene. 

### Splicing Pattern

Below the coordinates is a schematic of the splicing pattern of an example 
transcript from the gene.  This will give you an idea of the size of the UTR 
and exons for the gene visualized in the heatmap below.

## Heatmap

Below the gene visualization is the heatmap of allele frequencies.

### Rows

Rows in the heatmap are samples in the data set.  MBASED is a tool run on this 
data to identify genes that show evidence for ASE.  We applied a coverage 
cut off to the genes that went into MBASED, requiring at least ten reads from 
each allele of a particular SNP before MBASED could be run on the gene.  Sample 
names that are displayed in grey did not have any SNPs that met the coverage 
criteria and therefore these samples were not tested for ASE. Samples shown in 
black had at least one SNP that met the coverage criteria for MBASED.  Sample 
names shown in bold had a MBASED p-value < 0.05, indicating there is 
significant evidence for ASE in that sample.  Clicking on a sample name will 
link to the Sample page of the website where you will find more detailed 
information about the sample. As you scroll over the sample names a tooltip 
will appear over the sample name giving the MBASED p-value, if available.

### Columns

Columns in the heatmap are SNPs that were heterozygous for at least one of the 
samples in the data set.  The SNP is identified by its chromosome and position 
in the hg38 human reference genome.  Clicking on a SNP name will take you to 
the Myers lab JBrowse instance where you can explore the splicing pattern of 
the gene and examine the reads covering a particular SNP.

### Heatmap Cells

Each individual cell in the heatmap displays the frequency of the alternate 
allele in the read pileup over the particular SNP position in the sample 
listed. The color scale is displayed in the legend at the bottom of the page. 
Briefly, SNPs at standard homozygous allele frequencies (0% alternate allele 
or 100% alternate allele) are displayed in white, because they do not indicate 
any ASE. SNPs at standard 50% heterozygous frequency are displayed in yellow. 
Again SNPs at 50% do not indicate the existence of ASE.  At 25% and 75% 
alternate allele frequency, the cell will be blue and red, respectively. When 
alternate allele frequency is at these non-standard allele frequencies it is 
an indication of ASE in that SNP. Grey cells indicate that there were no reads 
covering that position in the sample, so there is no information available 
about that SNP. As you scroll over the cells in the heat map, a tooltip will 
display showing the number of reads at that position mating the reference base, 
the number of reads at that position matching the alternate base, the alternate 
allele frequency at that position, and the genotype of that position given by 
the microarray.
