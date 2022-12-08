# Redirect Link to Original Repo: click [here](https://github.com/davisatwell/learncli211/tree/master/workdir/Cache-Simulators)

## <img src = "https://img.shields.io/badge/Cache%20Simulators%20in%20C-davisatwell-9cf"/> 

three different versions of a cache simulator created by davisatwell
### *Direct Mapped Read-Only Cache*

  This version only needs to support reading bytes from an address.
  The number of set index bits determines the number of cache lines as each
  set only has one line. No replacement policy is specified because there is
  no choice for which line to replace. 

### *Fully Associative Write Through Cache*

  This version supports both reading and writing bytes from an address.
  There is only one set of cache lines so the number of set index bits is known
  to be zero. The number of cache lines is specified when the cache is created.

### *Set Associative Write Back Cache*

  This version implements a general set-associative cache with reading and writing
  with "write back". Within a set of cache lines, least recently used is the replacement
  policy. Write back means that when a byte is written, it is only written to the cache line
  without immediately updating main memory. A "dirty" cache line is written back in its entirety
  to the main memory when it is replaced. This version also supports "flushing" the cache which
  means writing back any dirty cache lines and invalidating all cache lines to reset the cache
  to empty.

## Main Memory Break Down

The following files are used to implement the underlying main memory. Do not edit or change:
* main_mem.h
* main_mem.c
* main_mem_log.c
* main_mem_log.h

The main memory implementation logs all read/write operations. The contents of main memory can be dumped/loaded
into a file using the functions *writeMainMemToFile* and *loadMainMemFromFile*. The log can be written out to a file
using the function *writeLogToFile*.

### DM Cache Disclaimer
Do not change the declarations of *createDMCache*, *freeDMCache*, or *readByte*.

### FA Cache Disclaimer
Do not change the declarations of *createFACache*, *freeFACache*, *readByte*, or *writeByte*.

### SA Cache Disclaimer
Do not change the declarations of *createSACache*, *freeSACache*, *readByte*, *writeByte*, and *flushCache*.
