---
title: Schedule
---  


<style>
details summary {
    width: 200px;
    display: block; 
}
</style>

<!-- --- 
| Date   | Topic | Materials | Lab |
|--------|-------|-----------|-----| -->

| Week | Lecture 1 | Lecture 2 |
|------|----------------------------------|--------------------------|
| Jan 14/16 | Introduction to Deep Learning Systems; GPU/Accelerator Overview [[Slides]](./S26-Week-0-Lect0-Background.pdf) | Intro to CUDA and GPU Arch Programming [[Slides 1]](./S26-Week-0-Lect1-Intro%20to%20CUDA.pdf) [[Slides 2]](./S26-Week-0-Lect2-GPU-Arch-Programming.pdf) |
| Jan 21/23 | Deep Learning Computer Vision [[Slides]](S26-Week-2-Lect1-Deep-Learning-Computer-Vision.pdf) | GEMM Operation Optimization [[Slides 1]](./S26-Week-2-Lect1-GEMM.pdf) [[Link 1]](https://penny-xu.github.io/blog/tiled-matrix-multiplication) [[Slides 2 ]](./S26-Week-2-Lect2-GEMM.pdf) [[Link 2]](https://www.aleksagordic.com/blog/matmul) |
| Jan 28/30 | Sparse Matrix Multiplication [[Slides]](./S26-Week-3-Lect1-SpMM.pdf) | PyTorch Customr C++ and CUDA Operators [[Slides]](./26-Week-3-Lect2-pytorch_extension.pdf) |
| Feb 4/6 | Guest Lecture - Jianming Tong [[Record]](https://rice.box.com/s/eidzagxnij6ihfq804w8vkl02tqa3vhh) | Convolution Operation [[Slides]](./S26-Week-4-Lect1-Convolution.pdf) |
| Feb 11/13 | Evolution & Programming of Tensor Cores [[Slides]](./S26-Week-5-Lect1-GPU-TensorCore.pdf) | *Spring Recess No Course* |
| Feb 18/20 | Transformer Ops & Float Format [[Slides 1]](./S26-Week-6-Lect1-Transformer.pdf) [[Slides 2]](./S26-Week-6-Data-Format.pdf) | TBD |
| Feb 25/27 | Distributed Training Fundamentals; Data vs Model Parallelism | S26-Week-8-Lect2-DistTrain.pptx — Distributed training implementation |
| Mar 4/6 | Communication Optimizations and Scheduling | S26-Week-9-Lect2-Diffusion.pptx — Diffusion models and compute scheduling |
| Mar 11/13 | Systems for Large Models (LLMs, Diffusion Models) | S26-Week-10-Lect2-DLRM.pptx — Deep Learning Recommendation Models |
| Mar 18/20 | Profiling, Benchmarking, and Performance Analysis | (TBD — profiling demo or tool lecture) |
| Mar 25/27 | Case Studies: GNN Acceleration, Diffusion Models, Recommender Systems | (Combine with prior GNN, Diffusion, and DLRM lectures as recap) |
| - Apr 24 | Course Presentation | Course Presentation


## Exteral Talk
| Date   | Lecturer | Topic | Materials |
|------|----------------|------------------|-------------------------|
| Feb 4 | Jianming Tong <div style="display: inline-block;"><details><summary style="display: block; width: 100%; max-width: 200px">Bio</summary>Jianming Tong (https://jianmingtong.github.io/) is a 4th-year PhD candidate at Georgia Tech, a visiting researcher at MIT. He focuses on full-stack optimizations—spanning model, system, compiler, and hardware—for enhancing both efficiency and privacy of AI systems. He proposed a framework to approximate non-linear ML operators as polynomials to be compatible with Homomorphic Encryption (HE) without utility sacrifice, enabling privacy-preserving ML via HE (model, MLSys'23), and developed the CROSS compiler to convert HE workloads as AI workloads to be accelerated by existing Google TPUs, enabling immediate scalable low-cost privacy-preserving capability to existing AI stacks and designed a dataflow-layout co-switching reconfigurable accelerator for efficient inference of dynamic AI workloads (ISCA'24). These works are widely deployed in NVIDIA, Google, IBM, and recognized by Qualcomm Innovation Fellowship and Machine Learning and System Rising Star.</details></div><div style="display: inline-block; margin-right: 10px;"><details><summary>Lecture Abstract</summary>The inference efficiency of diverse ML models over spatial accelerators boils down to the execution of different dataflows (i.e. different tiling, ordering, parallelism, and shapes). Using the optimal dataflow for every layer of workload can reduce latency by up to two orders of magnitude over a suboptimal dataflow. Unfortunately, reconfiguring hardware for different dataflows involves on-chip data layout reordering and datapath reconfigurations, leading to non-trivial overhead that hinders ML accelerators from exploiting different dataflows, resulting in suboptimal performance. To address this challenge, we propose FEATHER, an innovative accelerator that leverages a novel spatial array termed NEST and a novel multi-stage reduction network called BIRRD for performing flexible data reduction with layout reordering under the hood, enabling seamless switching between optimal dataflows with negligible latency and resources overhead. For systematically evaluating the performance interaction between dataflows and layouts, we enhance Timeloop, a state-of-the-art dataflow cost modeling and search framework, with layout assessment capabilities, and term it as Layoutloop. We model FEATHER into Layoutloop and also deploy FEATHER end-to-end on the edge ZCU104 FPGA. FEATHER delivers 1.27-2.89x inference latency speedup and 1.3-6.43x energy efficiency improvement compared to various SoTAs like NVDLA, SIGMA and Eyeriss under ResNet-50 and MobiletNet-V3 in Layoutloop. On practical FPGA devices, FEATHER achieves 2.65/3.91x higher throughput than Xilinx DPU/Gemmini. Remarkably, such performance and energy efficiency enhancements come at only 6% area over a fixed-dataflow Eyeriss-like accelerator. Our code is available at https://github.com/maeri-project/FEATHER.</details></div> | FEATHER | [[Record]](https://rice.box.com/s/eidzagxnij6ihfq804w8vkl02tqa3vhh) |
| Feb 25 | Hongzheng Chen <div style="display: inline-block;"><details><summary style="display: block; width: 100%; max-width: 200px">Bio</summary>Hongzheng Chen is a final-year Ph.D. candidate at Cornell University. His research interests broadly lie in compilers, programming systems, and accelerator architecture for generative AI workloads. He has authored 20+ papers in top-tier computer systems and hardware conferences. The machine learning systems resulting from his work have been widely adopted across industry, including Google, AMD, Intel, NVIDIA, AWS, and ByteDance. His research has received three Best Paper nominations and a Best Paper Award at leading hardware conferences, and he was selected as an ML and Systems Rising Star in 2024.</details></div><div style="display: inline-block; margin-right: 10px;"><details><summary>Lecture Abstract</summary>Theoretical scaling laws suggest that increasing compute should naturally lead to more intelligent models. In practice, however, moving a novel model architecture from research to efficient deployment on distributed heterogeneous systems reveals a large gap between theoretical promise and real performance. This gap arises from the hardware lottery of mapping models to chips, the software lottery where frameworks constrain efficient implementations, and the growing productivity bottleneck of manual optimization.

In this lecture, I will present our work on composable programming models that aim to close these gaps. I will discuss **accelerator programming languages** through Tawa [CGO’26], an automated compiler that generates warp-specialized GPU kernels from high-level programs, and **accelerator design languages** through Allo [PLDI’24], a Python-embedded framework for rapid generation of customized accelerators.

Finally, I will describe Magellan [C4ML CGO’26], an agentic system that uses large language models to evolve the compiler itself. Together, these efforts outline a path toward an automated stack that better aligns AI models with hardware, bringing realized performance closer to the promise of scaling.</details></div> | Composable Programming Models for AI Scaling | [TBD] |
| Mar 4 | Zishen Wan | [TBD] | [TBD] |