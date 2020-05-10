# Summary for rperf script

Run this script of your AIX server to estimate the rPerf rating for that particular LPAR (VM) based of the number CPUs and Machine-Type-Model using the official server rPerf ratings.

## See Article on the AIXpert Blog
- https://www.ibm.com/support/pages/get-rperf-performance-rating-your-aix-lpar


## Debug or Experiments or "What if?"
```
$ export LOOKUP=IBM,9119-FHB_4000_256
$ export CPUS=250
$
$ rperf -v 
rperf Debug mode using your shell variable LOOKUP
LOOKUP=IBM,9119-FHB_4000_256
rperf Debug mode using your shell variable CPUS
CPUS=250
Information is from public documents from www.ibm.com
-- - System p Performance Report
-- - System p Facts and Features Document
-- - Power Systems Facts and Features Document
lookup IBM,9119-FHB_4000_256
matchup 32 372.27 256 2978.16
calculate cpus=250 from 32 372.27
calculate cpus=250 from 256 2978.16
2908.36 rPerf estimated
$
```

But what I actually have on this server is:
```
$ rperf -v
Information is from public documents from www.ibm.com
-- - System p Performance Report
-- - System p Facts and Features Document
-- - Power Systems Facts and Features Document
Machine=IBM,9117-MMA MHz=4704 Rounded-MHz=4700 CPUs=3 CPUType=PowerPC_POWER6
lookup IBM,9117-MMA_4700_3
matchup 2 20.13 4 40.26 8 74.89 12 105.89 16 134.35
calculate cpus=3 from 2 20.13
calculate cpus=3 from 4 40.26
30.20 rPerf estimated
$
```
