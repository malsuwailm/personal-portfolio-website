---
title: "Deciphering Genomic Diversity: A Data-Driven Approach"
date: 2019-03-28T15:14:54+10:00
weight: 5
---

Analyzing genomic data across multiple species, this study delves into genome sizes, chromosome specifics, and nucleotide composition. It encompasses simulations of sequencing coverage and a detailed examination of GC content, shedding light on the diversity and complexity of genomic structures.

![genomic](https://i.ibb.co/wztqfJk/gdc-data-harmonization-pipeline-1.png)

## Abstract

In an era where genomic data is exponentially expanding, understanding the diversity and complexity of genetic information across various species is paramount. This project presents a comparative genomic analysis across a broad spectrum of organisms, ranging from plants and animals to bacteria and yeasts. By examining genome sizes, chromosome specifics, and nucleotide compositions, the study aims to uncover fundamental patterns and variations in genetic makeup, offering a window into the evolutionary relationships and functional genomics of diverse life forms.

## Objectives

- **Comparative Genomic Analysis:** To compare and contrast the genomic characteristics (such as genome size, chromosome count, and chromosome sizes) across various species.
- **Identification of Genomic Diversity:** To identify and quantify the diversity in genome structures among different species, including plants, animals, bacteria, and yeasts.
- **Foundation for Further Genomic Studies:** To provide a comprehensive dataset that can be used as a foundation for further research in genetics, molecular biology, and evolutionary biology.

## Relevance

This genomic analysis project showcases the efficient handling and management of large-scale genomic datasets, a fundamental aspect of data science that involves sophisticated data processing and management skills. The use of statistical methods and pattern recognition for analyzing genomic structures underscores the importance of these techniques in extracting meaningful insights from complex datasets. Additionally, the project emphasizes the role of data visualization in data science, illustrating how complex data can be presented in an understandable and informative manner. This aspect is crucial for effective communication and decision-making in data science. Furthermore, the project exemplifies the interdisciplinary nature of data science, highlighting its utility in bridging various scientific fields and fostering innovation. In essence, the approach to handling, analyzing, and visualizing complex genomic data in this project is a testament to the practical applications and versatility of data science methodologies in real-world research contexts.

## Methodology

### Genomic Data Collection and Analysis (Sections 1.1 - 1.5)

1. **Data Acquisition:**
      - The project utilizes genomic data from various species, including 'TAIR10', 'ce10', 'dm6', 'ecoli', 'hg38', 'tomato', 'wheat', and 'yeast'.
      - Each data file (*.chrom.sizes) contains information about chromosome sizes for the respective species.

2. **Data Processing:**
      - Python and Pandas are used for data manipulation.
      - A custom function, question_1, iterates through each genomic data file.
      - The function reads each file, extracting chromosome names and sizes, and calculates the total genome size, the number of chromosomes, and the sizes of the largest and smallest chromosomes, along with the mean chromosome length.

3. **Data Aggregation:**
      - Results are compiled into lists for each species, including genome size, chromosome count, and other metrics.
      - These lists are then combined into a structured Pandas DataFrame, providing a comprehensive overview for comparative analysis.

### Sequencing Coverage Simulation (Sections 2.2 - 2.4)

1. **Simulation Setup:**
      - A Python script simulates sequencing coverage for a 1Mbp genome using 100bp reads.
      - Random sampling is used to generate sequences, and the SequenceMatcher tool is employed to calculate coverage.

2. **Coverage Analysis:**
      - Two scenarios are analyzed: 5x and 15x coverage.
      - The number of reads needed for each coverage level is calculated (500 reads for 5x coverage and 1500 reads for 15x coverage).
      - Histograms of coverage distributions are plotted and overlaid with Poisson distributions for each scenario.

3. **Evaluation of Coverage:**
      - The number of bases with 0x coverage is computed.
      - The results are compared with Poisson expectations to evaluate the accuracy and efficiency of the sequencing.

### Nucleotide Composition Analysis (Sections 3.1 - 3.3)

1. **Sequence Data Extraction:**
      - The project analyzes the nucleotide composition of chromosome 22, extracting the sequence from a data file (chr22.fa).
      - The sequence is processed to count the occurrences of each nucleotide (A, C, G, T, and N).

2. **Window-Based Analysis:**
      - The chromosome is divided into 100bp non-overlapping windows (bins).
      - The number of bins containing at least one 'N' nucleotide is calculated.
      - For bins without 'N's, the GC content is calculated.

3. **GC Content Visualization:**
      - A histogram is created to visualize the distribution of GC content across the chromosome.
      - The histogram provides insights into the sequencing quality and regions that might sequence poorly.

## Comparative Genomic Analysis Across Multiple Species

| Species | Genome Size | Number of Chromosomes | Largest Chromosomes | Smallest Chromosome | Mean Chromosome |
|---------|-------------|-----------------------|---------------------|---------------------|-----------------|
| TAIR10  | 119146348   | 5                     | Chr1                | Chr4                | 23829269        |
| ce10    | 100286070   | 7                     | chrV                | chrM                | 14326581        |
| dm6     | 137547960   | 7                     | chr3R               | chr4                | 19649708        |
| ecoli   | 4639211     | 1                     | Ecoli               | Ecoli               | 4639211         |
| hg38    | 3088269832  | 24                    | chr1                | chr21               | 128677909       |
| tomato  | 782520033   | 13                    | ch01                | ch00                | 60193848        |
| wheat   | 14547261565 | 22                    | 3B                  | 6D                  | 661239162       |
| yeast   | 12157105    | 17                    | chrIV               | chrM                | 715123          |

## Data Visualization

Histogram representing the percentage of guanine (G) and cytosine (C) bases, commonly known as the GC content, in each bin of the chromosome, excluding bins that contain 'N' nucleotides. It plots the number of bins against their respective GC percentages. The x-axis represents the GC content percentage, while the y-axis shows the number of bins with that specific GC content.

![data1](https://i.ibb.co/JtZHPwt/Screenshot-from-2024-01-21-01-44-53.png)

The findings from chromosome 22 are then extrapolated to the entire human genome. The total genome size, computed in an earlier part of the project, serves as the basis for this extrapolation. By applying the proportion of poorly sequenced bases in chromosome 22 to the entire genome size, an estimate is made of the total number of bases in the human genome that could be sequenced poorly.

![data2](https://i.ibb.co/6y0yLHV/Screenshot-from-2024-01-21-01-45-05.png)

## Analysis

The project's comprehensive analysis began with the assessment of genomic data from eight different species, revealing a broad spectrum of genomic sizes and complexities. The data unveiled that the genome sizes ranged from as small as approximately 4.64 Mbp in E. coli to as vast as approximately 14.55 Gbp in wheat, illustrating the wide genetic diversity across species. Chromosome counts varied, with E. coli having a single circular chromosome, while humans (hg38) possess 24 distinct chromosomes. The largest chromosome identified was chromosome 1 in humans, spanning over 248 Mbp, whereas the smallest was the mitochondrial chromosome in yeast, underlining the vast differences in chromosome sizes and their potential functional implications.

The sequencing coverage simulations provided further insights. The histogram outputs from the 5x and 15x coverage simulations showed a skewed distribution of coverage, with a significant number of sequences falling below the expected average coverage, indicating potential sequencing gaps. The discrepancy from Poisson expectations suggested the presence of a bias in sequencing, which might be attributed to various biological factors such as GC content, which can affect the efficiency of sequencing.

The nucleotide composition analysis of chromosome 22 demonstrated a prevalence of adenine and thymine over cytosine and guanine, while a considerable amount of the chromosome comprised unidentified nucleotides (Ns). This was further quantified by the window analysis, where bins were analyzed for the presence of 'N's, and nearly 116,637 bins were found to contain at least one 'N'. The GC content histogram revealed a normal distribution, with a notable number of bins having extremely low or high GC content, which correlates with regions known to be difficult to sequence, hence likely to be sequenced poorly.

The visual data from the histograms indicated a significant portion of the genome with extreme GC content, which is known to pose challenges in sequencing due to secondary structures and polymerase bias. These results, extrapolated to the entire human genome, suggest that around 700,250 bins without any 'N's are expected to sequence poorly, further asserting the importance of understanding genomic composition for sequencing efforts.

## Conclusion

The findings from the comparative genomic analysis underscore the intricate diversity in genetic composition among species. The project highlighted the crucial interplay between genome size, chromosome structure, and nucleotide composition and their collective impact on sequencing. The histograms and statistical analyses provided a tangible representation of the sequencing coverage and nucleotide distribution, offering a microcosmic view of the genomic landscape. The study concluded that while technological advancements have significantly improved sequencing capabilities, challenges remain, especially in regions with high or low GC content, and in accurately representing repetitive sequences and regions with unidentified nucleotides. These insights not only contribute to the field of genomics but also enhance the understanding of genomic data's complexity, paving the way for improved sequencing techniques and more accurate genomic assemblies. The project stands as a testament to the pivotal role of data science in translating raw genomic data into actionable genomic knowledge.

## Faithful Representation

The analysis and results presented in the project accurately reflect the genomic data of the studied species. The methodology ensures a faithful representation of the data, minimizing biases and errors.

## Comparability

The structured approach and uniform data processing allow for a high degree of comparability across species. The use of consistent metrics and methods ensures that the comparisons are valid and meaningful.

## Understandability

The project is structured in a way that makes the complex data and findings accessible and understandable to a wide audience, including those who may not have an in-depth background in genomics.

### Source Code

The project is publicly available on my [Github Repository](https://github.com/malsuwailm/comprehensive-analysis-of-genomic-data-across-multiple-species) and is open for further contributions.
