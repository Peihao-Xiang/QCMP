---

# FULL PHD PROPOSAL STRUCTURE

*(Question-Conditioned Multimodal Perception for Efficient and Reliable Agentic AI)*

---

# 1. Project Summary

## 1.1 Overview

Concise description of:

* The fundamental scientific problem:
  * Limitation of bottom-up perception pipeline for modern multimodal AI systems:
	* Unnecessary computational cost
	* Early information loss caused by compression
	* Increased hallucination risk when reasoning lacks task-relevant evidence
	* Inefficient processing for real-time applications
  * Planning under hard safe and budget constraints:
	* Safety constraints
	* High-efficiency computing
  * Reliability and robustness under hallucination during planning and reasoning

* Theory of humans perform question-conditioned perception
  * Know the question in advance
  * Selectively attend to relevant information
  * Ignore irrelevant details

* The research approach (Question-Conditioned Multimodal Perception Mechanism [QCMP])
  * Outline LLM-driven Perceptual Planning Pipeline
	* The scene is interpreted by a VLM planner
	* The Multi-LLM planner generates a Perceptual Query Plan that specifies what evidence must be collected
  * Converts natural language questions into executable perceptual query plans
	* Multimodal perception tools are executed selectively under computational budgets
	  * Evidence requirements
	  * Perception actions
	  * Spatial and temporal scopes
	  * Computational budgets
  * Online Reasoning Pipeline
	* Structured evidence is collected before reasoning occurs
	* A reasoning module produces answers grounded in evidence

* The validation platform (real-time multimodal applications)
  * LLM-based planning
  * Multimodal perception
  * Evidence-grounded reasoning
  * Agentic control for information-loss mitigation
  * Application evaluation framework
	* Healthcare monitoring
	* Public safety
	* Intelligent video understanding

## 1.2 Intellectual Merit

Explicitly state: New theoretical and algorithmic foundations for goal-driven multimodal perception paradigm.

* Framework for Question-Conditioned Multimodal Perception
* Perceptual Query Planning with LLMs
* Loss-Aware Agentic Control
* Evidence-Grounded Multimodal Reasoning
* Budget-Aware Multimodal Orchestration

Together, these contributions will establish a new class of agentic multimodal perception systems that actively acquire information rather than passively encoding the world.

## 1.3 Broader Impacts

* Healthcare: Surgical safety and patient condition detection
  * Improved precision and reduced hallucination can enhance clinical safety

* Transportation Autonomous: Hazard detection and safety monitoring
  * This can improve autonomous driving safety

* Public Safety: Emergency detection and risk monitoring
  * Such systems improve situational awareness while reducing false alarms

* Industrial Monitoring: Defect detection and infrastructure monitoring
* Accessibility: Assistive visual systems

* Open-source multimodal perception frameworks
* Datasets for question-conditioned visual reasoning
* Educational materials for safe and explainable multimodal AI

# 2. Project Description

## 2.1 Introduction and Motivation

* Loss of representation-first paradigm (context, statistics)
  * CLIP
  * LLaVA
  * BLIP-2
  * Gemini

* Limitations of current multimodal AI:
  * Early information compression/loss
  * Inefficient computation
  * Increased hallucination during reasoning
  * Unsafe or opaque running approaches

* Gap in theory:
  * Lack of AI planning strategy for human perception is goal-driven
  * No design multimodal AI systems that adopt a similar top-down perception strategy

* Central hypothesis and research objectives
  * Aligning visual perception with question intent 
  * Significantly reduces hallucination
  * Improves efficiency
  * Preserves task-relevant information

## 2.2 Background and Related Work

### 2.2.1 Multimodal Representation Learning

* Multimodal Contrastive Self-supervised Learning (CLIP)
* Multimodal Masking Self-supervised Learning (FLIP)
* Multimodal Bootstrapping Self-supervised Learning (BLIP)
* Multimodal Representation Learning Limitations

### 2.2.2 Vision-Language Models/Multimodal LLMs

* Visual Instruction Tuning (LLaVA)
* Multimodal Module Architecture (VideoLLaMA)
* Multimodal Unified Architecture (Gemini)
* VLM&MLLM Limitations

### 2.2.3 Multimodal Agentic-Style AI

* Multimodal LLM Agent (GPT-4V Agent)
* Tool-Augmented Multimodal Agent (MM-ReAct)
* Multi-Agent Multimodal AI (MM-AutoGen)
* Embodied Multimodal Agent (World Model/Voyager) - Active Perception and Environment/Task-Driven Vision
* Multimodal Agentic-Style AI Limitations

Conclude with:

> No existing framework unifies reliable guarantees, constrained adaptation, efficient inference, and evidence-only reasoning.

## 2.3 Preliminary Results

### A. Multimodal Perception Modeling
“MultiMAE-DER: Multimodal Masked Autoencoder for Dynamic Emotion Recognition”

* Cross-modal masked autoencoding for representation learning
* Robustness to missing modalities
* Analysis of temporal representation structure in masked vision transformers

### B. Implicit Evidence Reasoning Analysis
“MTCAE-DFER: Multi-task Cascaded Autoencoder for Dynamic Facial Expression Recognition”

* Cascaded autoencoder architecture for temporal modeling
* Multi-task learning for robust feature representation
* Design of perception modules that extract structured visual evidence for reasoning

### C. Semantic Self-aware Alignment
“Label Ranker: Self-aware Preference for Classification Label Position in Visual Masked Self-supervised Pre-trained Model”

* Self-aware label ranking for classification token placement
* Visual representations interact with semantic tokens
* Aligning language queries with visual perception module

### D. Efficient Representation Mechanisms
“Entropy Reveals Block Importance in Masked Self-Supervised Vision Transformers”

* Entropy-based analysis of transformer block importance
* Identification of redundant computation in masked vision transformers
* Designing efficient perception modules with minimal information loss

### E. Query-Aware Multimodal Inference
“Answering by Asking: Query-Aware Visual Token Pruning for Efficient Vision-Language Models”

* Query-aware Adapter module for visual token filtering
* Cosine similarity between text tokens and visual tokens
* Prune visually irrelevant tokens before reasoning

Collectively, these results demonstrate the feasibility of building efficient, multimodal, and language-aware perception systems, which motivates the proposed research on question-conditioned multimodal perception for reliable visual reasoning.

## 2.4 Research Objectives and Questions

Structured around:

* RQ1: Scenes/Questions be converted into safe and executable perceptual query key intents/strategies
* RQ2: From tools pool acquire visual evidence under computational constraints (strict latency and compute budgets)
* RQ3: Perception-driven evidence-grounded reduce hallucination in multimodal planning/reasoning
* RQ4: Agentic controllers detect and mitigate information loss during fast perception

Include:

* Hypotheses
* Expected theoretical contributions

## 2.5 Technical Approach

This is the heart of the proposal.

### 2.5.1 System Architecture for Question-Conditioned Multimodal Perception

#### A. Outline Planning Pipeline

* Intent Interpreter
* Security Detector
* Perception Planner
* Policy Decision Maker

#### B. Online Reasoning Pipeline

* MCP Controller
* Tool Executor (Orchestrator)
* Evidence Reasoner

### 2.5.2 Perceptual Query Planner

* Query type
* Target entities
* Evidence requirements
* Spatial/Temporal scope
* Tool chain
* Fusion logic
* Safe rules

Example outputs include structured JSON plans specifying the perception pipeline.

### 2.5.3 Tool-Based Multimodal Perception Callback (Tool Registry)

* Capabilities
* Input/output schema
* Cost model
* Evidence type
* Reliability characteristics

The planner selects tools from this registry to form an executable perception pipeline.

### 2.5.4 Budget-Aware Orchestration

* Latency estimation
* Tool call limits
* ROI selection
* Adaptive sampling

The orchestrator ensures that plans respect computational budgets.

### 2.5.5 Evidence-Based Reasoner

* Object bounding boxes
* Segmentation masks
* OCR outputs
* Event detections

LLMs then produce answers grounded in this evidence.

### 2.5.6 Loss-Aware Agentic Controller

A novel Loss-Aware Agent monitors information loss risk during perception.

The agent estimates loss risk using signals such as:

* Temporal/Sampling coverage
* Planner uncertainty
* Tool reliability/confidence
* ROI coverage
* Input quality metrics
* Sensor quality

Based on these signals, the agent dynamically adjusts perception strategies:

* Expand temporal windows
* Increase sampling rate
* Invoke additional perception tools
* Escalate to human review if necessary

## 2.6 Experimental Validation Plan

### 2.6.1 Offline-Level Datasets Validation

Benchmarks:

* VQAv2
* GQA
* VizWiz

* MSRVTT-QA
* MSVD-QA
* NExT-QA

* ActivityNet Captions
* Charades
* Something-Something V2

* AVE
* VGGSound
* AudioSet

Metrics:

* Task Performance
  * Accuracy
  * BLEU / CIDEr
  * Recall@K

* Efficiency Metrics
  * Inference latency
  * FLOPs / compute cost
  * Number of perception tool calls
  * Number of visual tokens processed

* Evidence Grounding Metrics
  * Grounding accuracy
  * Localization IoU
  * Evidence recall
  * Explanation consistency

* Hallucination Metrics
  * Hallucination rate
  * Unsupported answer rate
  * Factual consistency
  * Possible evaluation methods:
  * Evidence verification
  * Human annotation
  * LLM-based factual checking

### 2.6.2 Real-time Scenarios Evaluation

Design:

* Healthcare Monitoring
* Transportation Safety
* Public Safety Monitoring

Metrics:

* Latency
  * End-to-end latency
  * Perception latency
  * Reasoning latency

* Responsiveness
  * Detection delay
  * Time-to-answer

* Compute Efficiency
  * GPU utilization
  * Number of tool invocations
  * Tokens processed per query
  * Energy consumption

* Reliability Metrics
  * False positive rate
  * False negative rate
  * Hallucination rate
  * Insufficient evidence rate

Statistical plan:

* Number of perception tools invoked
* Visual tokens processed
* ROI coverage
* Sampling FPS
* Evidence confidence

These statistics enable detailed analysis of information loss and perception planning effectiveness.

## 2.7 Risk Mitigation Strategy

Potential technical risks include:

### 2.7.1 Planning Errors

Mitigation:
* Redundant routing strategies
* Fallback detection strategies

### 2.7.2 Tool Failures

Mitigation:
* Multi-signal evidence fusion
* Cross-tool validation

### 2.7.3 Budget limitations

Mitigation:
* Adaptive sampling
* Hierarchical perception

### 2.7.4 Information Loss

Mitigation:
* Loss-aware adaptive perception
* Temporal buffer replay

## 2.8 Timeline and Milestones

3-month plan:

Month 1:

* QCMP Theory and Framework Design
* Prototype Implementation
  * Outline Planning Pipeline Implementation
  * Online Reasoning Pipeline Implementation

Month 2:

* Compensation/Correction Mechanism
  * Constraint Planning Algorithms
  * Tool Registry Design
  * Agentic Control Mechanisms
* Loss-aware Agent Development
* Large-scale Experiments

Month 3:

* Benchmark Validation
* Real-time Deployment
* Multi-domain Evaluation
* Dissertation Completion

Include:

* Milestone table
* Deliverables

## 2.9 Broader Impacts

The project advances trustworthy multimodal AI by:

* Reducing hallucination
* Improving computational efficiency
* Enabling explainable visual reasoning.

Results will benefit real-time applications including healthcare monitoring, safety systems, and assistive technologies.

# 3. References Cited

# 4. Facilities, Equipment, and Other Resources

Describe:

* Computing Infrastructure
* Multimodal Data Resources
* Software and Experimental Platforms
* Experimental Evaluation Environment
* Collaborative Research Environment

# 5. Data Management Plan (Required)

Include:

* Types of data collected
* Storage and backup
* De-identification procedures
* Dataset release timeline
* Software release plan
* Long-term archival plan

# Summary of Proposal Logic

The proposal narrative should follow this arc:

1. Gap: Modern multimodal AI systems rely on bottom-up perception pipelines, where images or videos are encoded before the system knows the question, leading to information loss, unnecessary computation, and hallucination during reasoning.

2. Question: This reveals a fundamental scientific problem: how to design Efficient multimodal AI systems in which perception is guided by task intent or user questions rather than fixed representations.

3. Hypothesis: We introduce a new paradigm that Question-Conditioned Multimodal Perception, where natural language questions drive perceptual planning and evidence acquisition before efficient reasoning.

4. Framework: We develop a computational framework for perceptual query planning and loss-aware perception, enabling multimodal systems to dynamically select relevant evidence under efficient computational and reliability constraints.

5. Approach: We design efficient multimodal inference mechanisms, including query-aware token selection, adaptive perception pipelines, and agentic controllers for managing potential information loss.

6. Validation: We validate the proposed framework through both offline multimodal benchmarks and real-time evaluation scenarios, measuring improvements in efficiency, evidence grounding, and hallucination reduction.

7. Impact: We disseminate the results through open-source frameworks, datasets, and benchmarks, enabling broader adoption of question-conditioned perception for reliable multimodal AI systems.

