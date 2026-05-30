---
layout: archive
title: "Tutorials"
permalink: /tutorials/
author_profile: true
---

A growing set of hands-on tutorials I write while learning and building LLM inference systems, LLM training systems, agent systems, and XPU programming. They are open source, code-first, and meant for engineers who want to understand how these systems actually work end to end. More will be added over time.

## LLM Inference Systems

- [**vLLM Learning Handbook**](https://jwzheng96.github.io/vllm-learning-book/) — A 46-chapter engineering handbook on LLM inference optimization, covering PagedAttention, continuous batching, KV cache management, source-code walkthroughs of vLLM internals, quantization and speculative decoding, distributed inference, and production deployment with monitoring. Targeted at engineers preparing for LLM infrastructure roles, integrating inference services into production, or contributing to vLLM itself.

- [**SGLang Learning**](https://jwzheng96.github.io/sglang-learning/) — A code-first tutorial on SGLang, covering its RadixAttention prefix cache, structured-generation frontend language, constrained decoding, and high-throughput serving runtime. Walks through source-code internals of the scheduler, batch manager, and backend executor, and shows how SGLang composes multi-turn, tool-using, and JSON-constrained workloads efficiently. Aimed at engineers who want to understand how SGLang complements vLLM-style inference and accelerates complex agent and structured-output pipelines.

## LLM Training Systems

- [**LLM Training Framework Tutorial Hub**](https://jwzheng96.github.io/llm-train-tutorials/) — A code-first tour of 15 major open-source LLM training frameworks, each with its own 13-chapter tutorial pinned to specific source commits. Covers pretraining and distributed foundations (Megatron-LM, DeepSpeed, ColossalAI, TorchTitan, nanotron, NeMo), fine-tuning stacks (LLaMA-Factory, ms-swift, Axolotl, Unsloth, XTuner), RLHF and post-training (TRL, OpenRLHF, verl), and general acceleration/PEFT. Aimed at engineers who want to understand training-system internals — parallelism strategies, memory and communication, and RLHF pipelines — by reading real framework code rather than just running scripts.

## Agent Systems

- [**From Hermes, Learn Agent**](https://jwzheng96.github.io/from-hermes-learn-agent/) — A code-level textbook that teaches how to build production-grade AI agents by reading the open-source Hermes Agent framework. The 14 chapters span agent fundamentals, the core conversation loop, tool systems, learning mechanisms, multi-platform architecture, and frontier work from 2024–2026, pairing Hermes source-code analysis with key papers and industry implementations such as ReAct, MemGPT, and Claude Code.

## XPU Programming

- [**Learn CUDA from Scratch**](https://jwzheng96.github.io/learn-cuda-from-scratch/) — A 14-chapter, code-first CUDA course that walks from thread models and memory hierarchies, through shared-memory optimization, reductions, GEMM, attention, and FlashAttention, and finally to building a GPT-2 inference engine from the ground up. Aimed at developers with C/C++ basics who want to understand how LLM inference actually runs on the hardware, rather than just calling existing frameworks.
