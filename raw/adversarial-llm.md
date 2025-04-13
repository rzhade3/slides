---
title: Adversarial Thinking for Large Language Models
theme: beige
---

# Adversarial Thinking for Large Language Models

---

### Alignment

LLMs have strong limitations that should be considered when designing an application that uses them

* Prone to:
	* Hallucination
	* Data leakage

---

### Data Privacy

Due to nature of LLM, it is possible to recover basically all training/ hydration data information from a model

* Any data that shouldn't be visible to a user should not be used to hydrate a model

---

### Tenancy

As stated above, LLMs are prone to data leakage. As such, user data (such as conversation history or context) needs to be access controlled properly

* User specific embeddings as well as conversation histories should have proper access control provided

---

### Hallucination

LLMs are prone to making up information

* Disallow ambiguity in queries; ensure that user questions and context is grounded in
* Allow "escape hatch" to allow users to either correct the model or 

---

### Prompt Injection

Apps that are designing to only answer questions with one context can be tricked into answering questions with a different context

* Ensure that the context of the question is properly grounded in the context of the conversation

---

## Security Services

1. Threat Model
	* Ensure alignment is correct
	* Provide recommendations on additional controls
2. Static and dynamic manual testing

