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
| Feb 4/6 | Guest Lecture - Jianming Tong [[Record]](https://rice.box.com/s/eidzagxnij6ihfq804w8vkl02tqa3vhh) | S26-Week-4-Lect2-Convolution.pptx — Convolution kernel optimization and dataflow |
| Feb 11/13 | Tensor Operations and Optimized Kernels | S26-Week-5-Lect2-Transformer.pptx — Transformer model and attention computation |
| Feb 18/20 | Compiler Techniques for Deep Learning (IR, Operator Fusion) | S26-Week-6-Lect2-SparseMM.pptx — Sparse matrix multiplication and graph IR |
| Feb 25/27 | Distributed Training Fundamentals; Data vs Model Parallelism | S26-Week-8-Lect2-DistTrain.pptx — Distributed training implementation |
| Mar 4/6 | Communication Optimizations and Scheduling | S26-Week-9-Lect2-Diffusion.pptx — Diffusion models and compute scheduling |
| Mar 11/13 | Systems for Large Models (LLMs, Diffusion Models) | S26-Week-10-Lect2-DLRM.pptx — Deep Learning Recommendation Models |
| Mar 18/20 | Profiling, Benchmarking, and Performance Analysis | (TBD — profiling demo or tool lecture) |
| Mar 25/27 | Case Studies: GNN Acceleration, Diffusion Models, Recommender Systems | (Combine with prior GNN, Diffusion, and DLRM lectures as recap) |
| - Apr 24 | Course Presentation | Course Presentation


## Exteral Talk
| Date   | Lecturer | Topic | Materials |
|------|----------------|------------------|-------------------------|
| Feb 4 | Jianming Tong <div style="display: inline-block;"><details><summary style="display: block; width: 100%; max-width: 200px">Bio</summary>Jianming Tong (https://jianmingtong.github.io/) is a 4th-year PhD candidate at Georgia Tech, a visiting researcher at MIT. He focuses on full-stack optimizations—spanning model, system, compiler, and hardware—for enhancing both efficiency and privacy of AI systems. He proposed a framework to approximate non-linear ML operators as polynomials to be compatible with Homomorphic Encryption (HE) without utility sacrifice, enabling privacy-preserving ML via HE (model, MLSys'23), and developed the CROSS compiler to convert HE workloads as AI workloads to be accelerated by existing Google TPUs, enabling immediate scalable low-cost privacy-preserving capability to existing AI stacks and designed a dataflow-layout co-switching reconfigurable accelerator for efficient inference of dynamic AI workloads (ISCA'24). These works are widely deployed in NVIDIA, Google, IBM, and recognized by Qualcomm Innovation Fellowship and Machine Learning and System Rising Star.</details></div><div style="display: inline-block; margin-right: 10px;"><details><summary>Lecture Abstract</summary>The inference efficiency of diverse ML models over spatial accelerators boils down to the execution of different dataflows (i.e. different tiling, ordering, parallelism, and shapes). Using the optimal dataflow for every layer of workload can reduce latency by up to two orders of magnitude over a suboptimal dataflow. Unfortunately, reconfiguring hardware for different dataflows involves on-chip data layout reordering and datapath reconfigurations, leading to non-trivial overhead that hinders ML accelerators from exploiting different dataflows, resulting in suboptimal performance. To address this challenge, we propose FEATHER, an innovative accelerator that leverages a novel spatial array termed NEST and a novel multi-stage reduction network called BIRRD for performing flexible data reduction with layout reordering under the hood, enabling seamless switching between optimal dataflows with negligible latency and resources overhead. For systematically evaluating the performance interaction between dataflows and layouts, we enhance Timeloop, a state-of-the-art dataflow cost modeling and search framework, with layout assessment capabilities, and term it as Layoutloop. We model FEATHER into Layoutloop and also deploy FEATHER end-to-end on the edge ZCU104 FPGA. FEATHER delivers 1.27-2.89x inference latency speedup and 1.3-6.43x energy efficiency improvement compared to various SoTAs like NVDLA, SIGMA and Eyeriss under ResNet-50 and MobiletNet-V3 in Layoutloop. On practical FPGA devices, FEATHER achieves 2.65/3.91x higher throughput than Xilinx DPU/Gemmini. Remarkably, such performance and energy efficiency enhancements come at only 6% area over a fixed-dataflow Eyeriss-like accelerator. Our code is available at https://github.com/maeri-project/FEATHER.</details></div> | FEATHER | [TBD] |
| Feb 18 | Hongzhen Chen | [TBD] | [TBD] |
| Mar 4 | Zishen Wan | [TBD] | [TBD] |