#### Compare the byte rate for reading bytes from SDRAM to that of the basic DRAM. Assume that the read cycle time $𝑡_{𝑅𝐶}$  for the basic DRAM is 60 ns and that the clock period $𝑡_{𝐶𝐿𝐾}$  for the SDRAM is 7.5 ns. 
**Solution** <br>
- The byte rate for the basic DRAM is one byte per 60 ns, or 16.67 MB/sec.
- For the SDRAM: 60 ns = 8 clock cycles, it means that SDRAM can read four bytes, giving a byte rate of 66.67 MB/sec. 
- If the burst is eight instead of four bytes, a read cycle time of 90 ns is required, giving a  byte rate of 88.89 MB/sec. 
- Finally, if the burst is the entire 2048-byte row of the SDRAM, the read cycle time becomes 60 + (2048 − 4) × 7.5 = 15,390 ns, 
- Giving a byte rate of 133.07 MB, which approaches the limit of one byte per 7.5 ns clock period.

####  Memory data path width: 
- **1 word = 4 bytes**
- **Burst size: 8 words = 32 bytes**
- **Memory clock frequency: 5 ns**
- **Latency time (from application of row address until first word available): 4 clock cycles**

**Solution** <br>
- Read cycle time:  (4 + 8) x 5 ns = 60 ns
- Memory Bandwidth: 32/(60 x 10-9) = 533 Mbytes/sec