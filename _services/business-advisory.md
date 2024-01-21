---
title: "Optimizing Genomic Analysis with Dynamic Programming"
date: 2018-12-28T15:14:39+10:00
weight: 4
---

Employing the Longest Common Subsequence (LCS) algorithm with a dynamic programming approach. Focused on analyzing DNA sequences, it efficiently identifies the longest common subsequences between given genetic strings, showcasing its applicability in sequence alignment, comparative genomics, and evolutionary studies. Using a 2D matrix for memoization, the project optimizes time complexity, enhancing performance for large biological datasets. It also encompasses testing and error handling for robust algorithmic execution, making it a valuable tool in the data-driven exploration of biological sequences.

![dna](https://i.ibb.co/0cmBKNL/table2-1.jpg)

## Abstract

The project advances the computational analysis of bioinformatics through the efficient application of the Longest Common Subsequence (LCS) algorithm, utilizing dynamic programming techniques. The project focuses on the pivotal role of LCS in identifying similarities within DNA sequences, a task fundamental to understanding genetic relationships and evolutionary patterns. By creating a robust algorithmic framework that handles various sequence complexities and incorporates rigorous testing, including extreme and erroneous cases, the project stands as a significant tool for bioinformatics researchers, providing both theoretical insights and practical applications in the field of data science.

## Objectives

1. Develop an LCS algorithm that effectively processes DNA sequences, accounting for both accuracy and efficiency in computation.
2. Test algorithmic robustness by validating input sequences and handling errors, ensuring the algorithm's reliability across diverse data scenarios.
3. Analyze the asymptotic complexity to understand the algorithm's scalability and performance, especially for large-scale bioinformatics datasets.
4. Document and visualize the performance through extensive testing, plotting execution times and comparisons to validate the algorithm's complexity class.

## Relevance

The LCS algorithm's relevance in data science and bioinformatics is substantial, serving as a cornerstone in sequence analysis, comparative genomics, and evolutionary biology. Its ability to extract the longest common subsequences from DNA strands aids in identifying evolutionary linkages, annotating genetic material, and predicting structural and functional aspects of genes and proteins.

## Methodology

1. **Algorithm Development:** The core of the methodology is the construction of the LCS algorithm using dynamic programming. This involves setting up a two-dimensional matrix to facilitate memoization, a technique that stores the results of subproblems to avoid recalculating them, thus saving computational resources.

2. **Input Sequence Processing:** The algorithm accepts sequences from user-defined files, with each sequence checked against a stringent set of criteria to ensure it is a valid DNA string. This step ensures that all subsequences processed are relevant to biological data analysis.

3. **Robustness Testing:** To evaluate the algorithm's robustness, it is subjected to a variety of test cases:
      
    - Normal cases are taken from typical DNA sequences.
    - Extreme cases involve sequences of repetitive nucleotides or exceptionally long strings to test the algorithm's upper limits.
    - Error-induced cases contain intentional faults, such as invalid characters, to ensure the algorithm can gracefully handle and report input errors.

4. **Performance Evaluation:** The algorithm is run against pairs of DNA sequences of increasing lengths. The execution time and the number of character comparisons needed for each operation are recorded to empirically determine the algorithm's performance.

5. **Asymptotic Complexity Analysis:** The collected data are used to plot the growth of execution time and comparison count against the sequence length. This step is crucial for understanding how the algorithm scales with input size.

6. **Output Generation and Documentation:** All results, including the LCS of sequences, the number of comparisons made, and the asymptotic cost table, are documented in a detailed output file. This ensures transparency and replicability of the results.

## Analysis


Asymptotic cost table

| Length | Execution Time | Comparisons |
|--------|----------------|-------------|
| 100    | 0.002497       | 10000       |
| 200    | 0.009906       | 40000       |
| 300    | 0.025328       | 90000       |
| 400    | 0.043761       | 160000      |
| 500    | 0.068062       | 250000      |


Asymptotic costs observed
![cost](https://i.ibb.co/qRV4hZ6/Screenshot-from-2024-01-20-23-48-23.png)


- The execution time increases quadratically as the length of the input sequences grows, which is consistent with the expected time complexity of O(mn)O(mn). This is indicative of the fact that for every increase in the sequence length, the time taken for computation grows by the square of the increase.

- The number of comparisons also shows a quadratic increase, further confirming the time complexity. The increase in comparisons is a direct measure of the algorithm's work as it processes each character pair in the sequences.

- The results show a clear correlation between the theoretical predictions of complexity and the observed empirical data, validating the algorithm's design and implementation.

- The algorithm demonstrates robustness across all test cases, including the successful handling of error-induced inputs, indicating its reliability in real-world applications.

## Conclusion

The LCS algorithm, developed and tested in this project, stands as a robust and efficient tool for sequence analysis, confirmed by its consistent performance across varying test conditions and its alignment with theoretical complexity models. The quadratic time complexity observed is typical for dynamic programming solutions to the LCS problem, and while it presents challenges for very long sequences, it remains an efficient approach for a wide range of practical applications in bioinformatics. The project's comprehensive methodology and rigorous analysis establish the algorithm as a reliable resource for researchers, with the potential to facilitate advances in genetic analysis, evolutionary studies, and other areas of computational biology. While the algorithm is efficient and reliable, future enhancements could explore reducing space complexity or adapting the algorithm for parallel computing environments, which could further extend its utility in processing the increasingly large datasets common in bioinformatics research today. The project's findings and outputs are documented with clarity and precision, ensuring that they can serve as a benchmark for future work in the area and as an educational resource for those looking to understand the practical applications of dynamic programming in data science and bioinformatics.

## Faithful Representation

The project faithfully represents the complexities inherent to bioinformatics data handling. The LCS algorithm's development and evaluation are conducted with rigor, ensuring that the outputs accurately reflect the algorithm's capabilities and limitations in real-world scenarios.

## Comparability

The LCS algorithm's performance is comparable to other sequence analysis algorithms in bioinformatics, providing a competitive solution for sequence alignment tasks. The detailed asymptotic complexity analysis allows for direct comparison with other algorithms, aiding in selecting the most suitable tool for specific research requirements.

## Understandability

The project is documented with a focus on understandability, ensuring that the methodology, analysis, and findings are accessible to both experts in the field and those with a foundational understanding of bioinformatics and data science. This approach not only demonstrates the algorithm's practical utility but also contributes to educational efforts in computational biology.

### Source Code

The project is publicly available on my [Github Repository](https://github.com/malsuwailm/lcs-genetic-analysis) and is open for further contributions.

### References

Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). Introduction to Algorithms (3rd ed.).
The MIT Press.

Gusfield, D. (1997). Algorithms on Strings, Trees, and Sequences: Computer Science and Computational
Biology. Cambridge University Press.

Hirschberg, D. S. (1975). A linear space algorithm for computing maximal common subsequences.
Communications of the ACM, 18(6), 341-343.

Needleman, S. B., & Wunsch, C. D. (1970). A general method applicable to the search for similarities in
the amino acid sequence of two proteins. Journal of Molecular Biology, 48(3), 443-453.

Smith, T. F., & Waterman, M. S. (1981). Identification of common molecular subsequences. Journal of
Molecular Biology, 147(1), 195-197.

Durbin, R., Eddy, S., Krogh, A., & Mitchison, G. (1998). Biological Sequence Analysis: Probabilistic
Models of Proteins and Nucleic Acids. Cambridge University Press.

Lesk, A. M. (2008). Introduction to Bioinformatics (3rd ed.). Oxford University Press.
Mount, D. W. (2004). Bioinformatics: Sequence and Genome Analysis (2nd ed.). Cold Spring Harbor
Laboratory Press.