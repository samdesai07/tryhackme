# Introduction
Q. I'm ready to learn about AI/ML security threats!
--> no answer needed.

## The Building Blocks of AI
Q. What category of machine learning combines both labelled and unlabelled data?
--> semi-supervised learning

Q. What is the first layer in a neural network that handles incoming raw data?
--> input layer

Q. Which learning method does not require human-labeled data and can extract features from raw, unstructured input?
--> deep learning

Q. What are the weighted connections between nodes in a neural network meant to simulate in the human brain?
--> synapses

KEY POINTS:
Artificial Intelligence (AI) is a broad field focused on creating machines that can perform tasks requiring human-like intelligence.
Machine Learning (ML) is a subfield of AI where computers learn from data without being explicitly programmed. It follows a structured lifecycle and uses algorithms like supervised, unsupervised, semi-supervised, and reinforcement learning.
Neural Networks are a type of ML model inspired by the human brain, with layers of interconnected nodes (neurons) that process data.
Deep Learning (DL) is a more advanced form of ML that uses neural networks with multiple hidden layers. A key advantage is its ability to learn from large, unlabeled datasets without human intervention, making it a "scalable" form of ML. The recent growth of DL is due to the availability of massive amounts of digital data.

## LLMs (Large Language Model)
Q. What type of AI model enabled major advancements in ChatGPT and similar tools?
--> Large Language Models

Q. What is the first training stage where an LLM processes massive amounts of data?
--> pre-training

Q. What type of neural network introduced by Google in 2017 powers modern LLMs?
--> transformer

KEY POINTS:
Large Language Models (LLMs) are a type of Deep Learning model that can process and generate text by predicting the next word in a sequence.
Pre-training: LLMs are initially trained on massive, unlabelled text datasets (like the entire internet), using billions of parameters to understand and generate human-like language. This is where they learn grammar, facts, and reasoning.
Transformer Neural Networks revolutionized LLMs by allowing them to process text in parallel, rather than word by word. This architecture, introduced in a 2017 paper, uses an "attention" mechanism to understand context and the relationships between words.
Reinforcement Learning from Human Feedback (RLHF): After pre-training, human feedback is used to fine-tune the model, adjusting its parameters to make responses more helpful and less problematic.
Generative AI: LLMs power Generative AI, a broader category that creates original content, including text, images, and music.
The Big Picture: AI is the overarching field, ML is a subfield, DL is a specialized branch of ML, and LLMs are an advanced form of DL, specifically enabled by transformer neural networks.

## AI Security Threats
Q. What framework was developed by MITRE to guide the understanding of AI-specific cyber threats?
--> ATLAS

Q. What type of attack involves cloning an AI model by interacting with its API?
--> model theft

Q.What generative AI technique can replicate a person’s voice or appearance with high realism?
--> deepfake

Q. What common social engineering attack has become harder to detect due to AI-generated fluent and convincing messages?
--> phishing

KEY POINTS:
AI Security Threats are divided into two categories: vulnerabilities in AI models themselves and the enhancement of existing attacks using AI.
Prompt Injection: Overriding a model's original instructions with new, malicious ones.
Data Poisoning: An attacker contaminates a model's training data to make its output biased or incorrect.
Model Theft: Stealing an AI model's intellectual property by querying its API to create a duplicate.
Privacy Leakage: A model unintentionally reveals sensitive data from its training set.
Model Drift: A model's performance degrades over time because the data it's processing changes.
Enhanced Attacks: AI significantly improves existing cyberattacks:
Malware: Generative AI simplifies and speeds up the creation of malicious code.
Deepfakes: AI generates highly convincing fake audio and video to impersonate people for fraudulent purposes.
Phishing: Generative AI creates more sophisticated, well-written, and personalized phishing emails that are harder for people to spot.

## Defensive AI
Q. According to IBM, how many days faster does AI help identify and contain breaches?
--> 108

Q. What cybersecurity task benefits from AI helping to imagine attacker behavior we might not consider?
--> threat hunting

Q. Explainability tools such as SHAP and LIME help with what?
--> Model Monitoring

KEY POINTS:AI is a powerful tool for cybersecurity defense that can be leveraged to analyze, predict, and investigate threats. While it introduces new vulnerabilities, securing AI models is crucial to maximize its benefits and combat AI-enhanced attacks.
How AI Defends Us
Analysis: AI uses Machine Learning to find anomalies and patterns in massive datasets at high speeds, which is essential for tasks like intrusion detection.
Prediction: AI models predict and automate security tasks, such as automatically blocking phishing emails.
Investigation: Large Language Models (LLMs) can summarize documents and logs, saving time and helping with incident investigation and threat hunting.
How We Secure AI
We must secure AI systems themselves to reap the benefits. This involves using MFA and RBAC to protect models, encrypting sensitive training data, and continuously monitoring models for signs of attack.

## Practical
What's the flag?
--> 
