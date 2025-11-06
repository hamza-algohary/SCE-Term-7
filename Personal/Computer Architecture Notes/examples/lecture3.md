#### 1. A 4M × 4 DRAM has a refresh time of 64 ms and the length of time to perform a single refresh per row is 60 ns. What is the refreshment time in case of distributed or burst refreshment. What is the time for Read & Write.

**Solution**<br>
no. of rows = 4096 rows to be refreshed.
##### Burst Refreshment: 
- A total time out for refresh = 4096 x 60 ns = 0.25 ms
- The rest time for R/W = 64ms – 0.25 ms = 63.75 ms
- The DRAM controller must initiate 4096 refreshes sequentially every 64 ms for burst refresh.

##### Distributed Refreshment
- the refresh interval for distributed refresh = 64 ms/4096 = 15.6 microseconds (μs).
- Time R/W = 15.6 μs – 60 ns
- The DRAM controller must initiate a refresh every 15.6 μs for  distributed refresh 

Since use of burst refresh would halt computer operation for a fairly long period, distributed refresh is more commonly used.


### Assignment
The refresh cycle is similar to READ cycle, but executing faster, Why?
