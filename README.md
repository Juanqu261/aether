# aether
The "invisible layer" between the business user's request and the final automated execution.

---

## **Project Core: "The Semantic Bridge"**

A platform that blends **Agentic RPA** (for the "dirty" web work) with **API Orchestration** (for the "clean" data work).

### **1. The Technical Stack**

| Layer | Technology | Role |
| --- | --- | --- |
| **Agent Engine** | `browser-use` + Playwright | Vision-based navigation & self-healing. |
| **Logic Layer** | **LangGraph** | Orchestrates loops between Browser and API tasks. |
| **Integrations** | **MCP (Model Context Protocol)** | Standardized "plugs" for Slack, GSuite, etc. |
| **State** | **Redis / PostgreSQL** | Session persistence (cookies) to bypass logins. |
| **Intelligence** | **Claude 3.5 Sonnet** | Top-tier reasoning for UI and tool calling. |

---

### **2. The "Plus" Features**

* **Session Vault:** Unlike raw scripts, your app saves browser states. The agent stays logged in like a real human.
* **Semantic Recording:** The agent records its first successful run as a "Semantic Map." If the site changes slightly, the AI heals the map instead of starting over.
* **Human-in-the-Loop (HITL):** A dashboard where the AI "calls for help" (e.g., for 2FA or CAPTCHAs) instead of just failing.
* **Automatic API Discovery:** If an MCP tool exists for a task, the system uses it; if not, it falls back to the browser.

---

### **3. System Architecture**

---

### **4. The "Semantic Map" Concept**

Instead of hardcoding `button#submit-v2`, your system saves the intent:

```json
{
  "step": 1,
  "action": "click",
  "target_description": "The primary green checkout button",
  "fallback_selector": "button.btn-primary",
  "api_equivalent": "/v1/checkout"
}

```

*If `button.btn-primary` disappears, the AI uses the description to find the new one.*
