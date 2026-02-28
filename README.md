# 🚀 Self-Hosted AI Infrastructure with DeepSeek Coder V2 LLM
### High-Performance, Secure LLM Platform for Coding & DevOps

---

## 📌 Overview

This project documents the design and implementation of a **self-hosted AI infrastructure** built to replace external AI SaaS platforms (e.g. Gemini, Claude, ChatGPT) in order to prevent sensitive data leakage while maintaining enterprise-grade performance.

### Objectives

- Eliminate dependency on external AI SaaS platforms  
- Prevent exposure of sensitive company data  
- Maintain high inference quality and low latency  
- Optimize for coding and DevOps workflows  
- Build a fully observable and secure production environment  

---

## 🔍 Model Evaluation & Selection

After benchmarking multiple open-source models, the following LLMs were selected:

- **DeepSeek Coder V2 (10B)**

### Selection Criteria

- Coding accuracy
- DevOps & infrastructure reasoning capability
- Latency and token throughput
- GPU memory efficiency
- Production inference compatibility

Codestral was chosen specifically for its strong code-generation capabilities.

---

## 🏗 Architecture

### Hardware

**Provider:** Hetzner (Dedicated Server – GEX131)

| Component | Specification |
|------------|---------------|
| CPU | 24 × Intel Xeon cores |
| RAM | 256 GB ECC DDR5 |
| GPU | NVIDIA RTX Pro 6000 |
| VRAM | 96 GB GDDR7 |

This configuration allows the 22B model to run fully in GPU memory for optimal throughput and low latency.

---

### Software Stack

| Layer | Technology |
|-------|------------|
| OS | Ubuntu 24.04 LTS |
| Containerization | Docker |
| Inference Engine | SGLang |
| UI | OpenWebUI |
| LLMs | DeepSeek Coder V2 |

---

## ⚡ Performance

Performance optimization focused on:

- Maximizing GPU utilization  
- Efficient KV cache usage  
- Optimized batching  
- Running models fully in VRAM  
- Reducing inference latency  

The resulting platform achieves performance comparable to external AI SaaS providers while maintaining full data sovereignty.

---

## 🔐 Security

Security was a primary design requirement.

### OS Hardening

- CIS Benchmark hardening (Ubuntu 24.04)
- Kernel live patching
- Firewall hardening
- SSH hardening

### Secure Access

- Cloudflare Zero Trust Tunnels
  - Secure SSH access
  - Secure Web UI access
- No publicly exposed ports

### Monitoring & Observability

- Prometheus
- NVIDIA DCGM (GPU monitoring)
- Docker metrics exporters
- System metrics exporters

Full visibility into:

- GPU health
- Container metrics
- System resources
- Inference performance

---

## 📊 Logical Flow

```
Users
   │
   ▼
Cloudflare Zero Trust
   │
   ▼
OpenWebUI (Docker)
   │
   ▼
SGLang Inference Engine
   │
   ▼
GPU (RTX Pro 6000)
   │
   ▼
LLMs (MinMax / Codestral)
```

---

## 🎯 Key Outcomes

- Eliminated external AI SaaS dependency  
- Prevented sensitive data exposure  
- Achieved high-performance GPU inference  
- Built fully observable AI infrastructure  
- Specialized LLM capability for coding & DevOps  

---

## 🚀 Future Improvements

- Quantization benchmarking (AWQ / GPTQ)
- Multi-GPU scaling
- Kubernetes orchestration
- SSO integration
- Internal knowledge-base fine-tuning

---

## 👨‍💻 Author

Senior DevOps Engineer specializing in:

- Cloud architecture  
- AI infrastructure  
- GPU optimization  
- Secure production environments  
- MLOps & LLM deployment  

---

*This repository demonstrates production-grade AI infrastructure design and secure LLM deployment in enterprise environments.*

