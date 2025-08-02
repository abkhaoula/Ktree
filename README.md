# 1. Paper Information

## Title: Khaoula Abdenouri, Karima Echihabi. KTree: a Kernel-Based Index for Scalable Exact Similarity Search

## Abstract: 

We propose the KTree, a balanced tree-based index for exact similarity search, with 𝑂 (𝑑 𝑙𝑜𝑔(𝑛)) average-case and worst-case search complexity, on a collection of 𝑛 𝑑-dimensional vectors. We present novel index building and query answering algorithms that leverage a new tight lower-bounding distance, a rich class of kernel-based splitting strategies, and a data-adaptive variance-guided segmentation that considers the best dimensions to join into segments regardless of their order. We establish theoretically the subsumption property of KTree’s splitting (i.e., that it subsumes all popular existing splitting strategies), the correctness of the lower-bounding distance, and the logarithmic average-case and worst-case search complexity. We demonstrate empirically the superiority of the KTree with aexhaustive experimental evaluation against state-of-the-art techniques, using query workloads of varying difficulty and four real datasets, including two out-of-core datasets containing 1 billion dense vector embeddings. The results show that the KTree outper- forms the second-best competitor (which is not always the same) by up to a 5.7x speed-up, a 2.2x better pruning ratio and a 15% tighter lower bound. We also conduct an ablation study that shows the impact of each key design choice on KTree’s performance.

## Paper Link:

# 2. Reproducibilty

## 2.1. Archive
This archive contains detailed information required to reproduce the experimental results of the above paper.

The archive contains the following 5 folders:

### code
This folder contains the code of the KTress index.

### data-queries
The data-queries subdirectory contains the datasets and queries used in the paper.


### paper
This folder contains the pdf of the KTree manuscript. 

## 2.2. Software Requirements
dependencies
- install eigen 3.4.0 library 
- after installation on ubuntu: run
	- cd /usr/local/include
	- sudo ln -sf eigen3/Eigen Eigen
- doxygen for docs

## 2.3. Hardware Requirements
No particular requirement other than a machine equipped with an HDD having at least 75GB of RAM. The experiments in the paper were run using GCC 6.2.0 under Ubuntu Linux 16.04.2 with default compilation flags. Experiments were conducted on a server equipped with two Intel(R) Xeon(R) Gold 6234 CPUs running at 3.30GHz, 125GB of RAM, and 135GB of swap space. The RAM was limited to 80GB3. Storage was pro- vided by a 3.2TB (2 × 1.6TB) SATA2 SSD array configured in RAID0, delivering a measured throughput of 330 MB/sec.
We used GRUB to limit the amount of RAM, restrict its size using the grub as follows:

sudo gedit  /etc/default/grub  \
add or update the GRUB_CMDLINE_LINUX_DEFAULT variable as GRUB_CMDLINE_LINUX_DEFAULT="quiet splash mem=75G" \
sudo update-grub \
sudo reboot 

 
