# 🦞 OpenClaw Sandbox: macOS + UTM + Kimi K2.5

A secure, "blast-radius zero" implementation of the **OpenClaw** personal AI assistant. This setup isolates the autonomous agent within a **UTM Virtual Machine (macOS)** and bridges communication via **Telegram**, leveraging **Kimi K2.5** for high-reasoning agentic tasks.

## 🏗️ Architecture

* **Orchestrator:** [OpenClaw](https://openclaw.ai/) (Local AI Gateway)
* **The Brain:** **Kimi K2.5** (1T parameter model) via **Ollama Cloud**
* **The Sandbox:** **UTM** running a virtualized macOS instance
* **Interface:** **Telegram Bot** for remote tasking and proactive updates

## 🚀 Quick Start (Ollama Workflow)

I followed the February 2026 [Ollama Integration Guide](https://ollama.com/blog/openclaw) to link the cloud models:

1.  **Install OpenClaw:**
    ```bash
    curl -fsSL [https://openclaw.ai/install.sh](https://openclaw.ai/install.sh) | bash
    ```
2.  **Launch & Configure:**
    ```bash
    ollama launch openclaw --config
    ```
    *Select **Kimi K2.5** as the model and **Telegram** as the messaging channel during setup.*

## 🛡️ Why a UTM Sandbox?

Giving an autonomous agent full access to your host machine is a security risk. This setup mitigates that by:

* **System Isolation:** The agent only has access to the virtualized macOS environment.
* **Snapshotting:** Before running complex tasks, take a UTM snapshot. If the agent makes a mistake, simply **Revert to Snapshot**.
* **Network Control:** Control exactly what the agent can access outside the VM.

## 🧪 Verified Tasks
- [x] **File Management:** Organized messy directories and handled VM-specific configs.
- [x] **Web Research:** Used the `browser` skill to summarize docs and DM them to Telegram.
- [x] **Proactive Monitoring:** Configured `HEARTBEAT.md` for the agent to monitor background processes and ping my phone on failure.

---
*Note: OpenClaw was previously known as Clawdbot and Moltbot.*
