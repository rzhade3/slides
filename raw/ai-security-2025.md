---
title: AI Security in 2025
theme: black
transition: slide
---

# AI Security in 2025
### Or: How I learned to stop worrying and love the agent  

---

## About Me  
- Product Security Engineer  
- **Rahul Zhade**  
- [GitHub](https://github.com/rzhade3)  

---

## Agenda  
1. Intro to AI  
2. SDLC Vulnerabilities from AI  
3. Product Vulnerabilities through AI  
4. Responsible AI Design  
5. Incident Response  

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
  - CI, Copilot Suggestions, DryRun, etc.  

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

## Module: Product Vulnerabilities from AI  

---

### Types of Vulnerabilities  
**Data Lifecycle**  
- Sensitive Info Disclosure  
- Data/Model Poisoning  

**Infrastructure**  
- Supply Chain Vulns  
- Unbounded Consumption  
- Model Theft  

**Emergent Issues**  
- Prompt Injection  
- Improper Output Handling  
- Excessive Agency  
- Hallucination  

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
- Differential Privacy (if needed)  

---

### Infrastructure  
> AI Infrastructure is non-trivial  

- Expensive, custom  
- Unsafe defaults  

---

### Infrastructure Controls  
- CI/CD pipelines (e.g., Wiz)  
- Rate limiting  
- Logging  

---

### Emergent Issues  
> People don’t know how to use AI  

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
- Don’t allow unsanitized output in sensitive contexts (UIs, shells)  
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

### Prompt Injection

![Prompt Injection](./public/ai-security-2025/prompt-injection.png)

---

### Prompt Injection Controls  
- Clearer context  
- Content filtering  

---

### Hallucination / Misinformation  
- Inform users of AI limitations  
- HITL: Keep human in the loop  

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

---

## Appendix
  
- [Adversarial AI Reading List](https://github.com/rzhade3/adversarial-ai-reading-list)  
- [saif.google](https://saif.google/)  
- [embracethered.com](https://embracethered.com/)
