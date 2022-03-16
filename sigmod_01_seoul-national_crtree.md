# Optimizing multidimensional index trees for main memory access

🔎    **Tags**                 <span style="background-color:  #e0b0ff;border-radius:5px;">Cache-conscious Index</span>    <span style="background-color:  #e0b0ff;border-radius:5px;"> In-memory Index </span>   
🧟    **Authors**              Kihong Kim, Sang k. Cha, Keunjoo Kwon      
🚏    **Venue**               SIGMOD   
📅    **Year**                 2001   
🕦    **Created**              March 15, 2022  
⏳    **Status**                Not Complete  
🔗    **Paper**                https://dl.acm.org/doi/abs/10.1145/376284.375679   



# What?
They propose CRTree: a cache-conscious R Tree

# Why?
For in-memory indexes memory access is the new bottleneck because of the gap between the CPU and DRAM speed. Each memory (DRAM) access costs 10x processor cycles, whereas each cache (SRAM) access costs 1/2 processor cycles.


# Takeaways
* To improve the cache behavior of an index, reduce the height of thre tree, i.e., increase the fan out of thre tree. (not applicable for R-tree since the keys of a R-tree node is much larger: eliminating only chlid pointers will not be able to free up enough space to pack more entries in a node)
    * eliminate child pointers from a node
    * set node size = n * cache block size  


# Details
Desiderata for MBR compression:
- Overlap check without decompression: To check the overlap between the query rectangle and a MBR DO NOT DECOMPRESS the compressed MBR. Rather COMPRESS the query rectangle ONE-TIME for overlap checks
- Simplicity: It should be computationally LIGHTWEIGHT and shold be performed with the CACHED data

