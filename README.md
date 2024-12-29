# Tutorial for TinyChat: Optimizing LLM on Edge Devices

This is a lab for [efficientml.ai course](https://efficientml.ai/).

Running large language models (LLMs) on the edge is of great importance. By embedding LLMs directly into real-world systems such as in-car entertainment systems or spaceship control interfaces, users can access instant responses and services without relying on a stable internet connection. Moreover, this approach alleviates the inconvenience of queuing delays often associated with cloud services. As such, running LLMs on the edge not only enhances user experience but also addresses privacy concerns, as sensitive data remains localized and reduces the risk of potential breaches.

However, despite their impressive capabilities, LLMs have traditionally been quite resource-intensive. They require considerable computational power and memory resources, which makes it challenging to run these models on edge devices with limited capabilities.

In this lab, you will learn the following:
* How to deploy an LLaMA2-7B-chat with TinyChatEngine on your computer.
* Implement different optimization techniques (loop unrolling, multithreading, and SIMD programming) for the linear kernel.
* Observe the end-to-end latency improvement achieved by each technique.

## Evaluation results of this finished repo
```
-------- Sanity check of reference implementation: Passed! -------- 
Section, Total time(ms), Average time(ms), Count, GOPs
reference, 2504.263916, 250.425995, 10, 1.046791

-------- Sanity check of loop_unrolling implementation: Passed! -------- 
Section, Total time(ms), Average time(ms), Count, GOPs
loop_unrolling, 2021.270996, 202.126999, 10, 1.296927

-------- Sanity check of multithreading implementation: Passed! -------- 
Section, Total time(ms), Average time(ms), Count, GOPs
multithreading, 705.130981, 70.513000, 10, 3.717664

-------- Sanity check of simd_programming implementation: Passed! -------- 
Section, Total time(ms), Average time(ms), Count, GOPs
simd_programming, 1594.031006, 159.403000, 10, 1.644535

-------- Sanity check of multithreading_loop_unrolling implementation: Passed! -------- 
Section, Total time(ms), Average time(ms), Count, GOPs
multithreading_loop_unrolling, 572.153015, 57.215000, 10, 4.581711

-------- Sanity check of all_techniques implementation: Passed! -------- 
Section, Total time(ms), Average time(ms), Count, GOPs
all_techniques, 199.865997, 19.986000, 10, 13.115987

All tests completed!
```


## TinyChatEngine

This tutorial is based on [TinyChatEngine](https://github.com/mit-han-lab/TinyChatEngine), a powerful neural network library specifically designed for the efficient deployment of quantized large language models (LLMs) on edge devices. 

![demo](assets/figures/chat.gif)

## Tutorial document

Please check this document and follow the instructions which will walk you through the tutorial: https://docs.google.com/document/d/13IaTfPKjp0KiSBEhPdX9IxgXMIAZfiFjor37OWQJhMM/edit?usp=sharing

## Submission

* Report: Please write a report ([form](https://docs.google.com/document/d/17Z_ab8EhDvjcigLXdDqMqd2LTVsZ4CnpOYNkRTrnTmU/edit?usp=sharing)) that includes your code and the performance improvement for each starter code. 
* Code: Use `git diff` to generate a patch for your implementation. We will use this patch to test the correctness of your code. Please name your patch as `{studentID}-{ISA}.patch` where {ISA} should be one of x86 and ARM, depending on your computer.

## Related Projects

[TinyChatEngine](https://github.com/mit-han-lab/TinyChatEngine).

[TinyEngine](https://github.com/mit-han-lab/tinyengine).

[Smoothquant](https://github.com/mit-han-lab/smoothquant).

[AWQ: Activation-aware Weight Quantization for LLM Compression and Acceleration](https://github.com/mit-han-lab/llm-awq)

## Acknowledgement

[llama.cpp](https://github.com/ggerganov/llama.cpp)

[transformers](https://github.com/huggingface/transformers)
