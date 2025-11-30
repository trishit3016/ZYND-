# Insta-Triage (powered by Neural Nexus)

**Tagline:** A Decentralized, Zero-Trust Emergency Grid

## 🚨 What is Insta-Triage

Insta-Triage is a proof-of-concept multi-agent emergency dispatch system designed to reduce “Golden Hour” delay by enabling secure, decentralized, and high-speed coordination between ambulances, hospitals, and routing agents.  
It uses a multi-agent architecture built on top of the ZyndAI Agent SDK for identity, encrypted messaging & discovery — combined with LLM-powered parsing for rapid emergency request handling, routing/ETA calculations, and fallback support for legacy systems.

## 🎯 Features (Planned / Implemented)

- Dispatcher agent that parses freeform dispatcher input into structured emergency requests (location, severity, patient info).  
- Broadcast to multiple Hospital agents simultaneously (parallel swarm dispatch).  
- Secure, cryptographically-verified identity (DID + credentials) for all agents.  
- “First valid accept” winner-takes-all logic to assign hospital in minimal time.  
- Timeout-based fallback to legacy/manual dispatch when no hospital agent responds.  
- (Optional / Demo-mode) Routing & ETA estimation agent (simulated or real) to compute ambulance travel time.  
- (Optional / Demo-mode) Ambulance / Responder agent to simulate dispatch, en-route status, arrival & handover.  
- Logging & audit trail: request times, responses, acceptances, fallback usages, routing/ETA, status updates.  
- (Future / Optional) UI (CLI or Web) to visualize dispatch flow, hospital assignment, ETA, status.  

## 🛠️ Tech Stack

| Component | Technology / Framework |
|----------|------------------------|
| Agent infrastructure (identity, secure messaging) | ZyndAI Agent SDK (DID, credentialing, MQTT, agent discovery) |
| LLM-based parsing & reasoning | Large-Language Model (e.g. via Cerebras inference layer) + LangChain / LangGraph for orchestration |
| Asynchronous / concurrent execution | Python 3.10+, `asyncio` |
| Inter-agent communication / pub-sub / messaging | MQTT (via Zynd SDK) |
| Routing & ETA (demo / simulation) | Mock routing module / mapping API or stub logic |
| Logging & state tracking | Python logging or lightweight DB / file-based logs |
| (Optional) UI / Demo interface | CLI / Streamlit / Flask / simple web UI |
| Configuration / Environment | `.env`, config files (e.g. hospital list, credentials), secure credential storage |

## 🚀 How to Set Up & Run (Dev / Demo Mode)

1. Clone the repository  
2. Install dependencies (e.g. `pip install -r requirements.txt`)  
3. Add `.env` with necessary credentials and configuration (agent seeds, broker endpoints, LLM credentials if any)  
4. Initialize agent identities (via Zynd SDK)  
5. Start core agents: Dispatcher + one or more Hospital agents (and optionally Routing, Ambulance, Fallback)  
6. (Optional) Start UI server for demo / monitoring  
7. Use the Dispatcher interface (CLI or UI) to input emergency requests and observe dispatch flow, logs, and final assignment  

*(Detailed step-by-step instructions to be filled once codebase structure is finalized.)*

## 🧪 Demo Scenario & What It Shows

- Dispatch a sample emergency request (e.g. “m 40 cardiac Market Rd”) via Dispatcher  
- Show parsing → structured JSON output  
- Show broadcast to hospital agents → verify DID → accept by first hospital  
- Show assignment & confirmation, routing/ETA (if implemented), and (if simulation) ambulance status flow  
- Show fallback path if no hospital responds (after timeout)  
- Provide logs / timestamps demonstrating dispatch → accept latency, decision flow, fallback or success  

## 👥 Team & Contribution Guidelines

*(You can list team members and their responsibilities here — use this template to reflect your 3-person team distribution.)*

## 📄 Limitations & Future Work

- This is a proof-of-concept: routing/ETA and ambulance-status are simulated (not real GPS / real ambulances)  
- Credential issuance / DID verification currently assumes trusted setup (for demo only) — real-world deployment would need robust identity issuance & revocation.  
- No medical triage logic or ambulance resource management implemented — only hospital availability is considered.  
- System assumes network connectivity and relies on Zynd infrastructure / broker; network failures or broker issues may impact reliability.  
- For real-world EMS use, many additional modules (real-time traffic, on-road ambulance tracking, hospital bed capacity, resource allocation, safety/ privacy, legal compliance) would be required.

## 📚 References & Acknowledgments

- Thanks to ZyndAI Agent SDK for decentralized identity & secure messaging foundation  
- Inspired by multi-agent system design principles and emergency dispatch system requirements.  
- (Add any research papers, libraries, or external resources used)  
