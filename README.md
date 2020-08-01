# BetterTiming
This is a small project of mine aiming to improve CPU timing in KVM to bypass certain anti-VM checks. It registers VM-exit for RDTSC instruction and then tries to offset it by the time spend in specified VM-exits.

**Disclaimer:** Testing was done only in an isolated environment. Doing such a change might introduce unwanted side effects to the guest OS.

## How to apply the patch
You will need to recompile Linux kernel from source. If you are on a distribution that has a custom build system, it might be easier to use it for building the kernel. The patch is currently for version 5.7.11, but you should be able to easily modify it for any new version of the kernel. 

1.) Download and extract kernel source
```
wget https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.7.11.tar.gz
tar -xf linux-5.7.11.tar.gz
cd linux-5.7.11
```

2.) 