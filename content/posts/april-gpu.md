---
title: "April GPU"
date: 2023-07-09T13:09:24+02:00
draft: false
---

## Getting April to use a GPU

### Current state of affairs

We live in days where there are constant wonders/horrors in the area of Machine Learning. 
For a long time this been the domain of a handful of tools.

- python
  - numpy
  - scipy
- jupyter
  - ipython
  - tensorflow
  - torch
  - pandas
  - matplotlib
- rapids
  * All of the above, but only for CUDA GPU's and optimized to keep the computations in GPU RAM.

### Where April fits in

April is just a APL compiler. At the moment it does a pretty good job of compiling APL on
the CPU and uses multiple cores. For most traditional APL programming this is probably
enough. But that is not why I got interested. I see the potential for using it as a tool
for Machine learning. I am a mathematician and today's libraries hide what is going on
inside. APL hides nothing. It is just a terse language for doing (mostly) linear
algebra. As such it fits a niche. People like me who want to understand what the machine is
doing when learning, not just cutting and pasting from online examples and hoping for the
best. For handling the huge arrays we see in Machine Learning fast enough we are going to
need to use the GPU.


### How do we do it

April is the work of few people with limited time and resources. As such a huge cross
platform solution like [mojo](https://www.modular.com/mojo) was out of the question.
Also I didn't want Vendor lock in and only rely on NVIDIA CUDA. In my research I also came
across Vulcan. I started to realize that shaders can be general compute nodes, just like
CUDA threads. Also it is possible to set up a compute pipeline in Vulcan without graphics
output. In fact displaying graphics is a extension in Vulcan and not part of the Vulcan
core. 

![targets](/images/spir.jpg)

Vulcan accesses shaders in a binary cross platform format called SPIR-V.
SPIRV-V is compiled to native code on the platform. It can be computed on AMD, NVIDIA and
on MAC's with Metal. SPIR-V is also accessible trough OpenCL making work on devices like
[XILINX Kria](https://www.xilinx.com/products/som/kria.html) which is a FPGA with ARM
cores and Mali. It can thus be used on mobile, desktop and robotics platforms.
Pretty cool!

### Overall design

This is all a preliminary sketch. None of this has been build yet. Nevertheless I have a
idea of how the structure is going to be.

Here is a sketch of the design.

![targets](/images/april-gpu.svg)


### GPU pipeline

This follows rather rigid design dictated by Vulkan.

Here is a sketch of the design.

![targets](/images/april-vulkan.svg)
