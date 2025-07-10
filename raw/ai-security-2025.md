---
title: AI Security in 2025
theme: black
transition: slide
---

# AI Security in 2025
### Or: How I learned to stop worrying and love the agent

---

## About Me

- **Rahul Zhade**
- Product Security Engineer
- [GitHub](https://github.com/rzhade3)

---

## Agenda
1. Intro to AI
1. SDLC Vulnerabilities from AI
1. Product Vulnerabilities from AI
1. MCP Security
1. Responsible AI Design
1. Incident Response

---

## Module: Intro to AI

---

### AI Lifecycle

![AI Lifecycle](./public/ai-security-2025/ai-lifecycle.png)

---

### Secure AI Framework

![Secure AI Framework screeenshot](./public/ai-security-2025/saif.png)

---

### AI vs Traditional Security

- Unstructured Inputs
- Side Channels
- Non-determinism
- Lack of explainability
- Greenfield! Lack of standards

---

### AI Usages in Software

- **Constructive**
  - Copilot, Cursor, etc.
- **Defensive**
  - Copilot Suggestions
- **Integrated**
  - Rest of this talk :)

---

## Module: Security Considerations for AI SDLC

---

### AI Usages in SDLC
- **Constructive:**
  - Copilot, Cursor, etc.
- **Defensive:**
  - CI, Copilot Suggestions, etc.

---

### Constructive AI Risks

- Prone to hallucinations
  - e.g., Package squatting
- Can scoop up data
  - Context may contain sensitive info

---

### Controls to Apply

- Properly review suggested code
- Use context exclusions
- Plan architecture in advance
- Add context via comments
- Use static/dynamic analysis

---

### Defensive AI

- More context-aware than SAST
- Easier rule writing
- Still prone to hallucinations, prompt injection

---

## Module: Product Vulnerabilities

---

### Types of Vulnerabilities

| Data Lifecycle | Infrastructure | Emergent Issues |
|----------------|----------------|-----------------|
| Sensitive Info Disclosure | Supply Chain Vulns | Prompt Injection |
| Data/Model Poisoning | Unbounded Consumption | Improper Output Handling |
| | Model Theft | Excessive Agency |
| | | Hallucination |

---

### Data Lifecycle

> AI is leaky!

- Inputs can be repeated verbatim
- Side channels
- Huge training datasets
- **Control:** Only use trusted, secure data

---

### Data Lifecycle Controls

- PII Redaction
- Careful Data Selection
- Differential Privacy (if possible)

---

### Infrastructure

> AI Infrastructure is non-trivial

- Expensive
- Bespoke dependencies
- Unsafe defaults

---

### Infrastructure Controls

- CI/CD pipelines (e.g., Wiz)
- Rate limiting
- Logging

---

### Emergent Issues

> People don't know how to use AI

- Ambiguous intent
- Misunderstood APIs
- Prompt Injection, Excessive Agency, etc.

---

### Improper Output Handling

> Output from LLMs must be sanitized

![Improper Output Handling](./public/ai-security-2025/xss.png)

---

### Controls

- Context-aware output encoding
- Don't allow unsanitized output in sensitive contexts (UIs, shells)
- Use HITL for state changes

---

### Excessive Agency

> AI may hallucinate or take wrong actions

![Excessive Agency](./public/ai-security-2025/excessive-agency.png)

---

### Controls

- Human in the Loop (HITL)
- Responsible agent design
- Educate users

---

### Hallucination / Misinformation

- Inform users of AI limitations
- HITL: Keep human in the loop

---

### Hallucination Controls

- Use Retrieval Augmented Generation (RAG)
- Off topic filtering

---

### Prompt Injection

![Prompt Injection](./public/ai-security-2025/prompt-injection.png)

---

### Types of Prompt Injection

* User Prompt Injection (UPIA)
  - Jailbreaks, etc.
* Cross Prompt Injection (XPIA)
  - MCP Vulnerabilities, etc.

---

### Prompt Injection Controls

- Clearer context
- Content filtering
- Dual LLM paradigm
- Nanny Agents
- [CaMeL](https://arxiv.org/abs/2503.18813)/ Information Control Flow

---

## Module: MCP Security

---

### Issues with MCP

* Authorization
* Supply Chain
* XPIA Risk
* Context Poisoning

---

### Using MCP Safely

1. Audit source code for any local MCP
1. Use credentials with least privilege
1. Use firewalls to ensure agents stay on guardrails
1. Properly define resources and tools

---

### MCP Security Specifications

* [Enhanced Tool Definition Interface](https://arxiv.org/html/2506.01333v1)
* Oauth 2.0 Support

---

## Module: Responsible AI

---

### Good Design Prevents Footguns

---

### Human in the Loop

- Protect users from themselves

---

### AI Disclosures
- Disclose all AI usage
- Explicit user consent for state-changing actions

---

### Content Filtering

- Prevent harmful/off-topic content

---

### Agentic Security Principles

1. Make sure agents can be turned off
1. Network interactions should be logged
1. Log who initiated the action, and input context
1. Run workflows in ephemeral environments
1. Do not use user secrets unless explicitly defined

---

## Module: Incident Response for AI

---

### Principles

- Logging & Monitoring
- Rate Limits
- Generous Logging (Reproducibility is hard)
- Set Customer Expectations

---

## Conclusion

---

### Key Takeaways

- Secure the whole AI lifecycle
- **Responsible AI Design!**
  - HITL HITL HITL
- Same risks, higher stakes
- Don't trust AI blindly

---

## Appendix

- [Adversarial AI Reading List](https://github.com/rzhade3/adversarial-ai-reading-list)
- [embracethered.com](https://embracethered.com/)
- [Simon Willison Blog](https://simonwillison.net/tags/security/)
