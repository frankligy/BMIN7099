# summary of gene annotation module

Without annotation, obtained sequence is not of much usage. To annotate genome, we need to collect some prominent sequence features to assist the process.
The easiest way to represent these sequence features are position weight matrix (PWM).

A related question is motif finding algorithm. The first problem is finding known motif (given a PWM) within a set of input sequences, this is relatively easier if we can just take the product of the probablity of the observed nucleotide, and count the number of sequences that contain product above a certain threshold. 

Finding novel motif is more challenging, if we have `t` strings of length `n`, we want to find motif that of length `m`:

1. Naive solution casts the problem as aligning the input sequence in a way that gives rise to minimum entropy. The time complexity is $O(mn^{t})$.

2. Alternative solution casts the problem as finding median string that minimize the hamming distances between median strings and all inputs. The time complexity is $O(tnm4^{m})$.

3. Other solution including representing the observed seqeunce as data and try to estimate the parameters of the underlying probabilistic distribution. See [MEME](https://pubmed.ncbi.nlm.nih.gov/7584402/).

We can utilize efficent data structure (suffix tree) to reduce the operation for both solution. 

The actual annotation requires both prior-collected sequence features (motif, stop codon, branch site, etc), along with dedicated computational algorithms. In addition to that, we also need experimental evidence (including various sequencing data on different modalities - DNA, RNA, regulatory regions, etc). See detailed [description]((https://www.sciencedirect.com/topics/biochemistry-genetics-and-molecular-biology/genome-annotation)).

