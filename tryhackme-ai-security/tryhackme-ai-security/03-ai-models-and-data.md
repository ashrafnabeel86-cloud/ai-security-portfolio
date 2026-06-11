# AI Models & Data

## Summary

This write-up documents my learning from the TryHackMe **AI Models & Data** room. The room focused on how training data, model building, fine-tuning, model inheritance, and third-party model repositories can introduce security risks into AI systems.

The main lesson was that AI security starts before a model is deployed. Risks can appear during data collection, training, validation, optimisation, fine-tuning, and model integration.

## What I Learned

### 1. Training Data Security

AI models depend heavily on training data. If the data is poorly sourced, unverified, biased, or contains sensitive information, the model may inherit those risks.

Key risks include:

* unclear data sources
* weak data provenance
* personal information in training data
* unlicensed or scraped data
* poisoned or manipulated data
* lack of filtering or documentation

A strong AI security process should track where data came from, when it was collected, how it was cleaned, and whether it contains sensitive information.

### 2. Data Provenance and ML-BOM

Data provenance means being able to explain where training data came from, when it was collected, and whether it was modified.

An ML-BOM is similar to a Software Bill of Materials. It documents important information such as dataset sources, licences, PII categories, and filtering decisions.

This is important because AI systems can inherit hidden risks from their data supply chain.

### 3. Building the Model

This section explained important training concepts such as epochs, overfitting, validation, pruning, quantisation, and federated learning.

Key points:

* An epoch is one complete pass through the training data.
* Overfitting happens when a model memorises training data instead of learning general patterns.
* Validation helps check whether the model performs well on unseen data.
* Pruning removes less useful parts of a model to make it smaller.
* Quantisation reduces numerical precision to make the model faster and lighter.
* Federated learning trains models across different devices or organisations without sharing raw data.

From a security view, these steps matter because they can affect privacy, model behaviour, reliability, and trust.

### 4. The Inheritance Problem

Most organisations do not train large AI models from scratch. Instead, they use pre-trained models and fine-tune them for specific tasks.

Fine-tuning improves the model for a specific use case, but it does not remove all risks from the original base model.

Inherited risks can include:

* bias from the base model
* unsafe behaviour
* weak safety alignment
* unknown training data issues
* vulnerable or undocumented model versions
* hidden supply chain risks

This means AI models should be treated like third-party software. The source, version, training history, and documentation should be checked before use.

### 5. The Black Box Problem

AI models can be difficult to understand because they contain billions of model weights. These weights store what the model has learned, but they do not clearly explain why the model makes a specific decision.

This creates risk in high-impact environments such as healthcare, finance, recruitment, compliance, and security operations.

A model card helps reduce this problem by documenting what the model is, how it was trained, what it should be used for, and what its limitations are.

### 6. Practical Model Audit

In the practical task, I reviewed a simulated model repository called `enterprise-classifier-v2`, designed to classify enterprise documents.

I checked the model card, file list, metadata, training details, licence, and organisation information for security concerns.

Key audit findings included:

* The model publisher was not verified.
* The organisation was new and had limited trust history.
* Training data was described vaguely as public web sources.
* There was no clear mention of PII filtering.
* The licence was custom and unclear.
* The model was fine-tuned from a base model, creating inheritance risk.
* Evaluation results were limited and did not include detailed security testing.
* The model was intended for sensitive enterprise workflows.
* The repository contained a `.pkl` model file, which can create supply chain risk because pickle files may execute code when loaded.

## Real-World Scenario

A company wants to use a third-party AI model to route internal documents such as support tickets, procurement requests, compliance queries, and internal communications.

If the model has vague training data, unclear licensing, no PII filtering, an unverified uploader, and a risky `.pkl` file, the organisation may introduce legal, privacy, operational, and security risks into its internal systems.

For example, a compliance document could be misclassified as a normal support ticket, causing sensitive information to be sent to the wrong team. If the model file is unsafe, loading it could also create a supply chain attack path.

## Skills Demonstrated

* Understanding AI data supply chain risks
* Recognising training data and privacy issues
* Explaining overfitting, validation, pruning, quantisation, and federated learning
* Understanding model inheritance risk
* Identifying black box model risks
* Performing a basic third-party model audit
* Connecting AI security concepts to real-world enterprise risk
* Documenting technical learning professionally

## Key Takeaway

AI security is not only about prompts and outputs. It also depends on the data pipeline, model training process, base model provenance, optimisation steps, documentation quality, file safety, and third-party supply chain trust.

Before integrating any third-party model into production, security teams should review the model card, training data, licence, file types, base model, version history, evaluation results, and publisher trust.

## New Vocabulary

**Training data**
The data used to teach an AI model.

**Data provenance**
The history of where data came from, when it was collected, and whether it was changed.

**ML-BOM**
A document that lists AI dataset sources, licences, PII categories, and filtering decisions.

**Epoch**
One complete pass through the training dataset.

**Overfitting**
When a model memorises training data instead of learning general patterns.

**Validation set**
Data used to test whether the model works on unseen examples.

**Pruning**
Removing less useful parts of a model to make it smaller.

**Quantisation**
Reducing numerical precision to make a model smaller and faster.

**Federated learning**
Training a model across multiple devices or organisations without sharing raw data.

**Pre-trained model**
A model already trained on a large general dataset.

**Fine-tuning**
Training a pre-trained model further on a smaller, specific dataset.

**Inheritance problem**
The risk that a fine-tuned model carries hidden issues from the original base model.

**Model weights**
The billions of numbers inside a trained model that store what it has learned.

**Model card**
Documentation that explains what a model is, how it was built, how it should be used, and its limitations.

**Supply chain risk**
Risk from using third-party models, files, datasets, or software.

**PII**
Personally identifiable information such as names, emails, addresses, account numbers, or medical details.

**Pickle / `.pkl` file**
A Python file format that can be risky because it may execute code when loaded.

## Note

This write-up does not include TryHackMe flags, passwords, or direct answer dumps. It is intended only to document learning, methodology, and professional development.
