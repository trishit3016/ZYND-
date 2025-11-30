# 📘 Insta-Triage (Powered by Neural Nexus)
### **A Decentralized, Zero-Trust Emergency Grid for Golden Hour Response**

---

## 🚨 Overview

**Insta-Triage** is a multi-agent emergency response system designed to cut Golden Hour delays from **minutes to milliseconds**.

It uses:

- **ZyndAI Agent SDK** → secure DID identity, encrypted MQTT messaging, and agent discovery  
- **Cerebras LLM** → fast emergency text parsing & triage  
- **Async Multi-Agent Architecture** → Dispatcher + Hospitals + Routing + Ambulance + Fallback  
- **UI Dashboard** → Live logs, status timeline, triage output, routing & ETA  

This project showcases how isolated agents can become an **intelligent decentralized network** capable of real-time medical coordination.

---

## 🧠 Core Idea (The Pitch)

Emergency dispatch today is **serial** and slow.

Insta-Triage introduces a **parallel swarm**:

1. Dispatcher enters messy shorthand:  
   **“m 40 chest pain market rd”**
2. Cerebras LLM parses it into structured JSON in 0.1s.
3. Dispatcher broadcasts to 10+ Hospital Agents simultaneously.
4. Hospital Agents cryptographically **verify Dispatcher DID** (Zynd SDK).
5. First valid hospital to accept is automatically assigned.
6. Routing Agent calculates **ETA**.
7. Ambulance Agent simulates **en-route → arrival → handover**.
8. If all fail → **Legacy Fallback** takes over.

---

## 🔥 Why This Project Matters

- Proves **secure multi-agent collaboration** (Zynd SDK requirement).
- Demonstrates **trust-based interoperability** (DID verification).
- Shows **parallelized dispatch** reducing golden-hour delays.
- Fully decentralized — no single central server required.
- Highly demo-friendly for hackathons.

---

# 🧩 System Architecture (6 Agents)

| Agent | Responsibility |
|-------|----------------|
| **1. Dispatcher Agent** | Parse input → broadcast → pick winner → trigger fallback |
| **2. Hospital Agents (N)** | DID verify → accept/reject → update availability |
| **3. Routing / ETA Agent** | Compute or simulate ETA & route |
| **4. Ambulance Agent** | Simulate dispatch → en-route → arrival |
| **5. Legacy Fallback Agent** | Trigger if no hospital responds |
| **6. UI/Monitor Agent** | Show logs, ETA, triage, agent statuses |

---

# 🧰 Tech Stack

### Core
- Python 3.10+
- **ZyndAI Agent SDK**
- AsyncIO (parallel swarm dispatch)

### LLM Layer
- **Cerebras Inference API**
- **LangChain / LangGraph**

### UI / Demo
- **Streamlit Dashboard**

---

# 🚀 End-to-End Project Flow

### 1. Dispatcher Input
User types:
