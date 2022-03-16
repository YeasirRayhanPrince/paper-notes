# Relaxed Operator Fusion for In-Memory Databases: Making Compilation Vectorization, and Prefetching Work Together At Last

🔎    **Tags**                 <span style="background-color:#ace5ee;border-radius:5px;">SIMD </span>    <span style="background-color:#ff9999;border-radius: 5px;"> Prefetching </span>  
🧟    **Authors**              Prashanth Menon, Todd C. Mowry, Andrew Pavlo    
🚏    **Venue**               VLDB   
📅    **Year**                 2017   
🕦    **Created**              March 15, 2022  
⏳    **Status**                Not Complete  
🔗    **Paper**                https://par.nsf.gov/servlets/purl/10066914  

## Why?
The most important performance criteria for an in-memory dbms is: a)cache misses to memory, b) computational throughput. (Not disk accesses any more)

## What?
They combine **SIMD** and **Prefetch** instructions using a new processing model called **relaxed operator fusion (ROF)** to tackle the case of cache misses and computational throughput


## Takeaways
- If dataset does not fit in cache, processor will stall because of memory accesses which will minimize the benefits of using SIMD
- Do not launch too many prefecteches within a short period of time (CPU will drop them when the buffer keeping track of the outstanding requests fill up)

## Jargons
*Operator Fusion*: combining the operation of multiple operators in a single iteration. 




