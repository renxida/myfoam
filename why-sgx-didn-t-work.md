# Why Sgx Didn't Work

From the Intel optimization manual, https://www.intel.com/content/dam/www/public/us/en/documents/manuals/64-ia-32-architectures-optimization-manual.pdf, page 2-19:

There are cases where the entire Decoded ICache is flushed. One reason for this can be an ITLB entry
eviction. Other reasons are not usually visible to the application programmer, as they occur when important controls are changed, for example, mapping in CR3, or feature and mode enabling in CR0 and CR4.
There are also cases where the Decoded ICache is disabled, for instance, when the CS base address is
NOT set to zero.


SGX didn't work because of this flushing?