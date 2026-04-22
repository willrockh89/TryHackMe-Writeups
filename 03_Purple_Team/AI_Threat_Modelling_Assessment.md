# Lab: AI Threat Modelling Assessment

## Room Metadata
- **Platform:** [TryHackMe](https://tryhackme.com/)
- **Category:** Purple Team / AI Security
- **Room:** [AI Threat Modelling Assessment](https://tryhackme.com/room/aithreatmodellingassessment)
- **Difficulty:** Easy
- **Status:** `Completed`

## Objective
**Goal:** Apply structured threat modelling methodologies to an Artificial Intelligence system. The objective was to identify AI-specific components, recognize unique vulnerabilities (such as data poisoning or model inversion), and implement strategic mitigations within a simulated architecture.

## Tools Used
* **Interactive Assessment App:** For simulating AI attack vectors and defensive shielding.
* **Architecture Diagramming:** Visualizing data flow and the placement of security controls.
* **Threat Modelling Framework:** Application of AI-specific attack surface modules to identify systemic risks.

## Methodology

### Phase 1: Guided Threat Identification
1.  **Scenario Analysis:** Analyzed seven distinct guided scenarios to identify core AI components, including Training Data, the Model itself, and Inference APIs.
2.  **Vulnerability Mapping:** Successfully mapped specific AI threats—such as **Data Poisoning** and **Model Inversion**—to their respective targets within the architecture.
3.  **Baseline Security:** Established the "Why" behind AI security, ensuring a foundational understanding of how machine learning vulnerabilities differ from traditional software bugs.

### Phase 2: Interactive Attack Simulation
1.  **Simulation Engagement:** Participated in three interactive attack simulations to test the resilience of a mock AI system.
2.  **Shield Implementation:** Strategically placed defensive "shields" (mitigations) on the prompt, the LLM Agent, Retrieval, and the Database to protect the model's integrity and user privacy. 
3.  **Verification:** Validated the hardening process by achieving a 100% completion rate, confirming that the mitigations effectively neutralized the simulated adversarial attempts.

---

## Key Findings
* **Key AI Vulnerability:** Identified the critical risk of **Data Poisoning**, where an adversary manipulates the training set to influence the model's future decision-making.
* **Flag 1 (Guided Questions):** `THM{threat_m0d3l_re4d1_}`
* **Flag 2 (Simulation):** `THM{AI_thr3at_m0dell3d}`

## Reflection
**Real-World Context:** Threat modelling for AI requires a shift from traditional infrastructure thinking to **Data Integrity** and **Model Robustness**. In the same way that a jet engine's performance depends on the purity of its fuel, an AI's output depends on the integrity of its training data. If an adversary "poisons" the data, the entire system's decision-making is compromised. This lab reinforces the need for "Defense in Depth" at the data, model, and interface layers—a principle that aligns with the high-precision quality assurance standards I practiced in aerospace maintenance.
