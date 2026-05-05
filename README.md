# 🧠 LLM-Powered Network Slice Negotiation Simulator

This repository contains an **asynchronous Python simulation framework** that models **multi-agent negotiation for resource allocation in 5G/6G network slicing**.

It simulates a negotiation process between two autonomous agents representing:

- 📶 **eMBB (Enhanced Mobile Broadband)**
- ⚡ **URLLC (Ultra-Reliable Low-Latency Communication)**

These agents leverage a **local Large Language Model (LLM)** to:
- Reason about network conditions
- Propose bandwidth allocations
- Generate counter-proposals

All decisions are guided by a **Digital Twin predictor**, with the goal of:

> ✅ Minimizing energy consumption  
> ✅ Strictly adhering to Service Level Agreements (SLAs)

---

## 🚀 Features

### 🤖 LLM-Driven Autonomous Agents
- Uses a **local LLM** for reasoning and negotiation
- Dynamic proposal generation with **concession pressure modeling**

### ⚡ 1B Model Optimization (`otel-llm-1b-it`)
- Tailored for **small, fast local models**
- Handles quirks of low-parameter LLMs

### 📊 Predictive Digital Twin (DT)
- M/M/1 queueing model
- CVaR (Conditional Value at Risk) for **tail latency prediction**
- Estimates:
  - Latency
  - Energy consumption

### 🔄 Asynchronous Negotiation Loop
- Built with `asyncio`
- Enables **parallel LLM calls**
- Reduces simulation runtime significantly

### 🛡️ Robust Fallback Mechanisms
- Regex-based parsing for malformed outputs
- Handles:
  - JSON failures
  - Schema hallucinations
  - String-to-number conversion issues

### 📈 Proportional Climb/Descent Logic
- Prevents:
  - Deadlocks
  - Overshooting
- Uses **PID-like adjustments** based on SLA violations

### 📉 Rich Metrics & Visualization
- Tracks:
  - Latency
  - SLA violations
  - Utility degradation
  - Energy savings
- Generates **CDF plots** using `matplotlib`

---

## 🛠️ Prerequisites & Installation

### 1. Environment Setup

Ensure you have **Python 3.8+** installed.

Install dependencies:

```bash
pip install numpy matplotlib openai
