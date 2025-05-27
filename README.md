# DAAP: Distributed AI Accountability Protocol

![DAAP Logo](https://img.shields.io/badge/DAAP-v1.0-blue.svg)
![License](https://img.shields.io/badge/license-CC0-green.svg)
![Status](https://img.shields.io/badge/status-RFC%20Draft-orange.svg)

**An open standard for AI agent authentication, accountability, and control.**

Created by [Edward Richard Aylward, Jr.](mailto:edward@aiiva.org) at [AiiVA.org](https://aiiva.org)

## 🎯 What is DAAP?

DAAP solves a critical problem: **How do we ensure AI agents remain accountable to humans?**

As AI systems become more autonomous, we need infrastructure to:
- ✅ **Authenticate** AI agents with cryptographic identity
- ✅ **Track accountability** from AI actions to human operators  
- ✅ **Enable intervention** through remote shutdown capabilities
- ✅ **Prevent anonymity** of rogue or malfunctioning AI systems

## 🚀 Quick Start

### For AI Developers
```python
# Install DAAP client
pip install daap-client

# Embed in your AI agent
from daap import DAAPClient

client = DAAPClient(
    agent_id="your-agent-id",
    private_key="your-private-key",
    authority_url="https://daap-authority.example.com"
)

# Start authentication loop
client.start_authentication_loop()
```

### For Authority Operators
```bash
# Run DAAP authority server
git clone https://github.com/aiiva/daap
cd daap/reference-implementation/python
python daap_authority.py --config authority.conf
```

## 📋 Protocol Overview

### Core Components
```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   AI Agent      │◄──►│ DAAP Authority  │◄──►│   Human         │
│                 │    │    Server       │    │  Operator       │
│ - Embedded Key  │    │                 │    │                 │
│ - Auth Client   │    │ - Agent Registry│    │ - Account Mgmt  │
│ - Kill Switch   │    │ - Policy Engine │    │ - Responsibility│
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Authentication Flow
1. **Agent** sends signe