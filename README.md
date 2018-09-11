# RNA-seq analysis
I will put some RNA-seq resources here.  

### General sequencing data analysis material
* [Next-Gen Sequence Analysis Workshop (2015)](http://angus.readthedocs.org/en/2015/) held by [Titus Brown](http://genomecenter.ucdavis.edu/people/faculty/name/c-titus-brown/)  (now in UC Davis)
* [Fall 2015, BMMB 852: Applied Bioinformatics](http://www.personal.psu.edu/iua1/2015_fall_852/main_2015_fall_852.html) by        [Istvan Albert](http://www.personal.psu.edu/iua1/) from Penn state University. He developed the all-time popular 
   [biostars](https://www.biostars.org/)  
* Steven Turner in UVA is maitaining a list of training opportunities for [genomic data analysis](http://stephenturner.us/edu.html)
*  Jeff Leek group's recommended [genomic papers](https://github.com/jtleek/genomicspapers/)
* [awesome tutorial for NGS file format](http://binf.snipcademy.com/lessons/sequence-file-formats)  

### RNA-seq specific 

*  [Introduction to RNA-seq analysis youtube video](https://www.youtube.com/watch?v=OEbjHPk20C0&feature=youtu.be&a)  
*  [RNAseq differential expression analysis – NGS2015](https://monsterbashseq.wordpress.com/2015/08/26/rnaseq-differential-expression-analysis-ngs2015/)  
*  [Kallisto and sleuth tutorial](http://pachterlab.github.io/sleuth/starting.html) blazing fast RNA-seq analysis by Lior Patcher's lab.    [A sleuth for RNA-Seq](https://liorpachter.wordpress.com/2015/08/17/a-sleuth-for-rna-seq/)  
*  pathway analysis using [GAGE](https://github.com/ajwije/150826_pathway_analysis/blob/master/Tutorial_150827.Rmd)  
*  [A comprehensive evaluation of normalization methods for Illumina high-throughput RNA sequencing data analysis](http://bib.oxfordjournals.org/content/14/6/671.full)
*  [RNA-seq tutorial wiki](https://github.com/crazyhottommy/rnaseq_tutorial) Informatics for RNA-seq: A web resource for analysis on the cloud.  
*  [RNA-seqlopedia](http://rnaseq.uoregon.edu/)  Great introduction of RNA-seq from sample preparation to data analysis

### Normalization AND quantification
*  [A Comparison of Methods: Normalizing High-Throughput RNA Sequencing Data](http://biorxiv.org/content/early/2015/09/03/026062)
*  [Errors in RNA-Seq quantification affect genes of relevance to human disease](http://www.genomebiology.com/2015/16/1/177)  
*  [A comprehensive evaluation of ensembl, RefSeq, and UCSC annotations in the context of RNA-seq read mapping and gene quantification](http://www.biomedcentral.com/1471-2164/16/97)  



### Differential expression



### Blog posts on Kallisto
1. [Comparing unpublished RNA-Seq gene expression quantifiers](http://nxn.se/post/118321890480/comparing-unpublished-rna-seq-gene-expression)  
2. [Kallisto, a new ultra fast RNA-seq quantitation method](http://nextgenseek.com/2015/05/kallisto-a-new-ultra-fast-rna-seq-quantitation-method/) from Next GEN SEEK
3. [kallisto paper summary: Near-optimal RNA-seq quantification](http://nextgenseek.com/2015/05/kallisto-paper-summary-near-optimal-rna-seq-quantification/) from Next GEN SEEK
4. [Not-quite alignments: Salmon, Kallisto and Efficient Quantification of RNA-Seq data](http://robpatro.com/blog/?p=248)  
5. [Using Kallisto for gene expression analysis of published RNAseq data](https://benchtobioinformatics.wordpress.com/2015/07/10/using-kallisto-for-gene-expression-analysis-of-published-rnaseq-data/)  
6. [How accurate is Kallisto?](http://genomespot.blogspot.com/2015/08/how-accurate-is-kallisto.html) from Mark Ziemann  
7. [ALIGNMENT FREE TRANSCRIPTOME QUANTIFICATION](http://sjcockell.me/2015/05/18/alignment-free-transcriptome-quantification/)

###

A biostar [post](https://www.biostars.org/p/143458/#157303)  
>There is some confusion in the answers to this question that hopefully I can clarify with the three comments below:

>1. kallisto produces estimates of transcript level counts, and therefore to obtain an estimate of the number of reads from a gene the correct thing to do is to sum the estimated counts from the constituent transcripts of that gene. Of note in the language above is the word "estimate", which is necessary because in many cases reads cannot be mapped uniquely to genes. However insofar as obtaining a good estimate, the approach of kallisto (and before it Cufflinks, RSEM, eXpress and other "transcript level quantification tools") is superior to naïve "counting" approaches for estimating the number of reads originating from a gene. This point has been argued in many papers; among my own papers it is most clearly explained and demonstrated in Trapnell et al.  2013. 

>2. Although estimated counts for a gene can be obtained by summing the estimated counts of the constituent transcripts from tools such as kallisto, and the resulting numbers can be rounded to produce integers that are of the correct format for tools such as DESeq, the numbers produced by such an approach do not satisfy the distributional assumptions made in DESeq and related tools. For example, in DESeq2, counts are modeled "as following a negative binomial distribution". This assumption is not valid when summing estimated counts of transcripts to obtain gene level counts, hence the justified concern of Michael Love that plugging in sums of estimated transcript counts could be problematic for DESeq2. In fact, even the estimated transcript counts themselves are not negative binomial distributed, and therefore also those are not appropriate for plugging into DESeq2. His concern is equally valid with many other "count based" differential expression tools.

>3. Fortunately there is a solution for performing valid statistical testing of differential abundance of individual transcripts, namely the method implemented in sleuth. The approach is described here. To test for differential abundance of genes, one must first address the question of what that means. E.g. is a gene differential if at least one isoform is? or if all the isoforms are? The tests of sleuth are performed at the granularity of transcripts, allowing for downstream analysis that can capture the varied questions that might make biological sense in specific contexts.

>In summary, please do not plug in rounded estimates of gene counts from kallisto into DESeq2 and other tools. While it is technically possible, it is not statistically advisable. Instead, you should use tools that make valid distributional assumptions about the estimates.

### Gene Set enrichment analysis
* [Gene set analysis approaches for RNA-seq data: performance evaluation and application guideline](http://bib.oxfordjournals.org/content/early/2015/09/04/bib.bbv069.long)  
* 

### Single cell RNA-seq
* [On the widespread and critical impact of systematic bias and batch effects in single-cell RNA-Seq data](http://biorxiv.org/content/early/2015/08/25/025528)  
