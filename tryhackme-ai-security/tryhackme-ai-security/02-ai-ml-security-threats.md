# TryHackMe AI/ML Security Threats – Write-Up

## Room / Topic

AI/ML Security Threats

## Date Completed

11 June 2026

## Objective

The purpose of this room was to understand common AI and machine learning security threats, how attackers can misuse AI, and how these risks affect modern cybersecurity.

## What I Learned

### 1. AI-Specific Security Threats

AI systems introduce new security risks because they depend on models, prompts, training data, APIs, and generated outputs. Attackers may target these parts of the system to manipulate behaviour, extract information, or cause incorrect results.

### 2. MITRE ATLAS

MITRE ATLAS is a framework focused on AI-related cyber threats. It helps explain how attacks against AI systems can happen, similar to how MITRE ATT&CK explains traditional cybersecurity attack techniques.

### 3. Prompt Injection

Prompt injection happens when a user tries to override the original instructions given to an AI system. This can cause the AI model to reveal information, ignore safety rules, or produce harmful or unintended outputs.

### 4. Data Poisoning

Data poisoning occurs when an attacker manipulates the data used to train an AI model. This can make the model produce incorrect, biased, or unsafe results.

### 5. Model Theft

Model theft happens when an attacker tries to copy or steal an AI model. This may happen through unauthorised access or by repeatedly querying an API and using the responses to train a similar model.

### 6. Privacy Leakage

Privacy leakage occurs when an AI model reveals sensitive information from its training data. This is a serious risk when models are trained on confidential data such as medical, financial, or personal information.

### 7. Model Drift

Model drift happens when an AI model becomes less accurate over time because the data or environment changes. This shows why AI systems need regular monitoring and retraining.

## AI-Enhanced Attacks

### Malware

Generative AI can make it easier for attackers to create or modify malicious code. This may lower the skill barrier for cybercriminals.

### Deepfakes

Deepfake technology can be used to copy a person’s voice or appearance. This creates risks for identity verification, fraud, social engineering, and business email compromise attacks.

### Phishing

AI can make phishing emails more convincing by improving grammar, tone, and personalisation. This makes phishing harder to detect using only spelling mistakes or poor writing as warning signs.

## Real-World Cybersecurity Connection

This topic is important for SOC analysts and cybersecurity professionals because AI is now being used by both attackers and defenders. Security teams need to understand AI-based threats so they can detect suspicious activity, protect sensitive data, and reduce the risk of AI misuse.

This knowledge can help with:

* Identifying AI-generated phishing emails
* Understanding prompt injection risks
* Recognising deepfake-based social engineering
* Protecting AI models and APIs
* Monitoring AI systems for unusual behaviour
* Explaining AI risks to non-technical staff

## What I Found Difficult

* Remembering the difference between data poisoning, model theft, and privacy leakage
* Understanding how traditional attacks like phishing become more dangerous with AI
* Connecting AI model risks to real-world SOC monitoring

## Revision Notes

I need to revise:

* MITRE ATLAS
* Prompt injection examples
* Data poisoning examples
* Deepfake risks
* AI-enhanced phishing

## Evidence

Screenshots or notes can be added here later.

> Note: This write-up does not include TryHackMe flags, passwords, or direct room answers. It only documents my learning and understanding.

## Reflection

This room helped me understand that AI security is not only about protecting normal computer systems. AI models, prompts, training data, and APIs can also become targets. I also learned that attackers can use AI to make traditional attacks such as phishing and social engineering more convincing. This topic is useful for building my cybersecurity portfolio because AI security is becoming increasingly relevant in modern organisations.
