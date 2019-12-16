# Review

## Info

Reviewer Name: Yi Chien
Paper Title: Unikernels: Library Operating System for the Clouds

## Summary
Unikernel is a library OS that is designed for cloud services. As library OS is not an new idea, but to facilitate the library OS on cloud service is new. Unikernel trims down the unnecessary modules of a kernel and leave only the essential and required part then compiled the whole kernel and application process into a single binary. Moreover, Unikernel is implemented in OCaml which means the kernel is type-safe and it reduce the attack-surface by cutting redundant code. However, reconfiguration requires Unikernel to recompile the whole image. 

### Problem and why we care
Cloud services run on an operating system that has too many unused feature running and this would waste the VMM's computation power, memory, and storage. To support more VMs on the same VMM, Unikernel not only reduces the size of the kernel but also has quick boot time and run time than before. Save more computation power means more VMs can be served and expand the capacity of VMM.

### Gap in current approaches
Library OS is not a new idea, but applying library OS targeting to cloud service has not yet been done before. Also, previous approaches runned on bare metal whereas Unikernel runs on top of hypervisor and saves the effort to implement device driver's effor. Unikernel uses a type-safe language and makes the final compiled image safer.

### Hypothesis, Key Idea, or Main Claim
Proposed the Unikernel and evaluate the performance with traditional applications running on monolithic kernel.

### Method for Proving the Claim
The authors implemented the library OS using Ocaml. The provided a step by step integration for applications to be ported from traditional Linux kernel to Unikernel by replacing the kernel step by step and produces the final single Unikernel image. 

### Method for evaluating
They evaluate the boot time between Unikernel and Linux PV, thread latency, network and storage, and several applications running on Unikernel versus Linux PV. Their comparisons are comparing to applications running on Linux kernel and comparison to different kernel like Exo-kernel or others.

### Contributions: what we take away
Unikernel is a fast and compact OS running on hypervisor for cloud services. It is safer and faster than Linux PV.

## Pros (3-6 bullets)
1. Type-safe
2. Quick boot time
3. QUick run time
4. Smaller image size
5. Without user and kernel mode switch

## Cons (3-6 bullets)
1. Clone image is not easy, need to recompile the code.
2. Reconfiguration means recompile
3. OCaml implementation introduces slight overhead compared to C
4. Applications can't share OS resources.

## Details Comments, Observations, Questions
Questions:
1. What is the difference between Unikernel and Microkernel?
2. What is the difference between Unikerenl and Exokernel?
3. Can we share the OS resources of Unikernel between different applications?
4. Do you think the evaluation is fair?
5. What are the situations most fit fot Unikernel?
6. How does Exokernel's performance compared to Unikernel?
