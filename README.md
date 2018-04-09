# Cache-Simulator

The simulator will take the provided input address trace as its input. It will implement the workings of the cache. Specifically, it will keep track of which blocks are brought into the cache and which blocks are being evicted. At the completion of the trace, the simulator will provide statistics about cache hit ratio, read traffic, write traffic etc.

1. Input trace: The simulator will take an address trace as its input. This trace captures the sequence of accesses that are being made to the cache. For each access, the trace provides the type of access and the memory address that is being accessed.
Each line in the trace has the following format:
Access_type Hex_Address
Access_type signifies the type of the memory operation (read or a write). It is encoded as a binary digit. Access_type = 0 indicates a read and Access_type = 1 indicates a write.
Hex_address is the address which is being accessed. The address is encoded in the hexadecimal (base-16) format. Each address is a 32-bit number (8 hexadecimal digits) and signifies the byte which is being accessed.
The two fields in each line are separated by a whitespace.
Example 1: Let us assume that the first line in the address trace is as follows:
0 00A53C00
This represents a read request to the byte address 0x00A53C00
Example 2: Let us assume that the second line in the address trace is as follows:
1 3C44DB20
This represents a write request to the byte address 0x3C44DB20
2. Cache Parameters: 
 Number of sets
 Associativity (Number of ways)
 Cache line size
To simplify the implementation, assume that each of the above three parameters will always be a power of 2. Also, the maximum associativity is 8 and the cache line size should range from 32 bytes to 128 bytes.
In addition, the modeled cache should implement a 1-bit LRU replacement policy. The details of the 1-bit LRU algorithm were discussed in class in Lecture 10.
As far as writes are concerned, you should assume a write-back cache with a write-allocate policy.
You don’t need to implement any timing details (such as hit time, miss penalty etc.) for the cache.
3. Simulator output: After the last access in the trace has been simulated, the simulator should output the following statistics:
 Total number of cache accesses
 Number of cache reads
 Number of cache writes
 Number of cache hits
 Number of cache misses
 Cache hit ratio
 Cache miss ratio
 Number of evictions
 Number of writebacks
