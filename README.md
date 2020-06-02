# Micro Map Reduce  

The Map Reduce framework was originally designed and implemented at Google to handle massive amounts of data processing for their search engine. The original Map Reduce framework abstracts away complex and  error prone code for Google scale parallel processing jobs by distributing Map and Reduce code across cheap commodity hardware. Using the constraints of Map and Reduce , simple code could be written that would otherwise be extraordinarily complex.

The essence of the Map Reduce framework is and has always been to process big data, massive parallel processing is necessary. But to make it simple,  we can constrain it to Map and Reduce jobs using this framework.

But what if the idea of using Map and Reduce jobs can solve more general data processing problems that have nothing to do with large scale data processing? That is what the Micro Map Reduce framework solves.

Think about it: If parallel code is always difficult to write what if a framework existed that could be imported into your codebase that could abstract away all parallel programming code no matter the use case? 

** This framework does this by implementing a Map Reduce interface over multi threaded single computer code rather than over commodity hardware. ** This allows for any job, not just massive parallel processing jobs, to be written in terms of Map and Reduce to simplify a codebase. 

This improves code performance drastically by taking advantage of multi threaded programming, dramatically simplifies the codebase by abstracting away complex multi threaded programming for any kind of job, and overall speeds up a teams workflow by not having to waste time on writing and debugging complex multi threaded code. 

## Current State Of Project and Limitations

All of the core logic is completely implemented and heavily tested for multiple worker failures.

The only further iteration necessary is packaging it into a useful product. The only roadblocks to that is it currently uses text files for local processing, so a simple interface to not need text files as input would need to be created. Also the codebase would have to be cleaned up a bit for packaging purposes. 

**The major limitation** to this project in it's current state is that it was implemented in Golang and not C. Golang's paradigms make it so it is already simple to implement multithreaded programming. Also Golang makes it so it can't be easily imported into a different language. This severely limits its practicality. 

For it to be practical and worthwhile, **it needs to be re-written in C**, and then used in C, C++, and Python (via C). This would make the framework incredibly useful in easily making any complex multiprocessing code very simple in languages where it is very hard (C, C++) or not as practical (Python - no native multithreading).
