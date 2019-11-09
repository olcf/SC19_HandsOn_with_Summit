[**Previous**](../XX)

# Bonus Cache

Recall that Summit's compute nodes are IBM AC922 servers, each with 2x 22-core Power9 CPUs. The [IBM AC922 Redbook](http://www.redbooks.ibm.com/redpapers/pdfs/redp5494.pdf) (technical product specification) reports that 512KB of L2 cache and up to 10MB of L3 cache is shared by each pair of cores. (Section 1.1, Page 3)

Variability is common in CPU manufacturing, and individual cores that do not meet minimum requirements may be disabled before being sold. This is a process known as [product binning](https://en.wikipedia.org/wiki/Product_binning).

Considering that pairs of cores in AC922 servers share L2 and L3 cache, disabling one core would give full cache access to the remaining enabled core.

This challenge is to find a disabled core on Summit among the compute nodes reserved for this event.
