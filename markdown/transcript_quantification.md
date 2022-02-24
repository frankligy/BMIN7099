# summary of transcript quantifications

Quantification of transcript is an important step for RNA sequencing data analysis.

Most straghtforward way to conduct quantification is based on the aligned record (where the reads were aligned), and see if the chromsome coordinates fall into the gene body, and then quantify the counts. One important problem is how to deal with multi-mapped reads, we use EM algorithm, I'd like to refer you to [this paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1475746/) for a clear explantion of the usage of EM in reads redistribution.

It is time consuming though, so we have alignment-free method. 

`Sailfish` divide the reference transcript and reads into kmer (usually 20mer), and store the reference transcript kmer as a hash function. So that the quantificaiton now has been casted to say if a kmer in a read is matched to a kmer in trancript or not, if so, that means this read comes from this transcript. 

More importantly, there are certain kmers that are linked to each other (i.e. kmer45 always co-occur with kmer67), we call them equivalent class, so it can further reduce the key in the hash of the reference transcript, query of kmer67 can be directly linked to kmer45.

Multi-mapping reads are still there, again, EM algorithm will be used to deal with that. `Sailfish` will discard reads that have mismatches.

While transformative, `Sailfish` divides the read to kmer which inherently ignores the valuable contextual information. `Kallisto` represents the transcript as De-Bruijn graph such that each kmer will be a node, transcript will help to construct the edges. Now we can simply traverse the graph for `pseudoalignment`.

