# Tailoring Software Security Requirements

## Overview
**Security by Design** is one of the fundamental pillars of product security  
The following outlines a **Software Security Requirements Tailoring Methodology**

---

## Methodology Phases

### 1. Threat Modeling
**Objective:**  
Identify security risks introduced by a new application or feature during the design phase

**Key Question:**  
> What needs to be protected, and against whom?

**Description:**  
Threat Modeling helps uncover potential vulnerabilities early in the design process, ensuring that protection mechanisms are defined based on identified threats and assets

---

### 2. Security Requirement Definition
**Objective:**  
Define the security countermeasures required to mitigate the identified risks, taking into account business and operational constraints

**Key Question:**  
> How will the application or feature be protected?

**Description:**  
This phase translates identified risks into actionable security requirements that guide design and implementation decisions

---

## Outcome
This methodology produces a comprehensive list of **Cybersecurity Requirements**
Each requirement is traced to the following elements:

- **Assets** – What needs to be protected?  
- **Threat Agents** – Against whom?  
- **Business Restrictions** – What constraints must be considered?

---

# Phase I: Threat Modeling

The cornerstone of this methodology is Threat Modeling, which identifies potential threats, quantifies associated risks, and defines appropriate mitigation measures.
The Threat Modeling process consists of the following steps:

1. Asset identification
2. Asset profiling
3. Threat Agent identification
4. Security Risks description
5. Risk rating (optional)

---

## Asset Identification 

An Asset is any data, dataset, privilege, communication flow, or other element that is important from a security perspective and requires protection

Identifying assets is an iterative process, as it is not always immediately clear which components of a product qualify as assets. In general, an asset is anything that can be **S**poofed, **T**ampered with, **R**epudiated, d**I**sclosed, **D**enied, or subjected to privilege **E**scalation

The outcome of the asset identification phase is a comprehensive list of assets:

| Asset Id      | Description |
| ------------- | ----------- |
| _Asset 1_     | _Personal identifiable information in the database_ |
| _Asset 2_     | ...                                                 |
| ...           |                                                     |

---

## Asset Profiling

Each Asset has its own characteristics and nature. Assets may be vulnerable to Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege

The outcome of the Asset Profiling phase is a matrix mapping Assets against STRIDE categories.
This matrix identifies whether Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service (DoS), or Elevation of Privilege affecting each asset could result in a cybersecurity risk

| Asset Id | Is Spoofing a risk? | Is Tampering a risk? | Is Repudiation a risk? | Is Disclosure a risk? | Is DoS a risk? | Is Elevation a risk? |
| -------- | ------------------- | -------------------- | ---------------------- | --------------------- | -------------- | -------------------- |
| _Asset 1_     | _Yes/No_       |                      |                        |                       |                |                      |
| _Asset 2_     | ...            |                      |                        |                       |                |                      |
| ...           |                |                      |                        |                       |                |                      |

---

## Threat Agent identification

Each system has its own specific Threat Agents, depending on its nature and environment. For example, the threat agents affecting a physical medical device differ from those targeting a cloud-based web application

Threat Agents can be classified as adversarial or accidental, based on their intent:

1. **Adversarial** Threat Agents act with the intention to harm the system. Examples include malicious actors with network access, rogue administrators, disgruntled employees, or ransomware

2. **Accidental** Threat Agents do not intend to cause harm but can still produce damage due to their access or influence. Examples include careless employees, environmental catastrophes, or software defects

The outcome of the Threat Agent Identification phase is a list of Threat Agents relevant to the scope of the new application or feature

| Threat Agent Id  | Description                                              | Intent      |
| ---------------- | -------------------------------------------------------- | ----------- |
| _Threat Agent 1_ | _Rogue System administrator with access to the database_ | Adversarial |
| _Threat Agent 2_ | ...                                                      |             |
| ...              |                                                          |             |

---

## Security Risk Description 

Identify how Threat Agents can Spoof, Tamper, Repudiate, Disclose, Deny, or Elevate sensitive Assets. Use the Threat Agent List and the Asset Profiling Matrix as inputs

The outcome of this Security Risk Description phase is a list of security risks in the following form:

| Risk Id  | Threat Agent Id | Can do                            | On Asset Id | How                             |
| -------- | --------------- | --------------------------------- | ----------- | ------------------------------- |
| _Risk 1_ | Threat Agent 1  | Information Disclosure            | Asset 1     | By accessing the database files |
| _Risk 2_ | ...             |                                   |             |                                 |
| ...      |                 |                                   |             |                                 |

In general, all risks must answer the questions: Which Threat Agents can harm the Assets? And how?

---

## Risk Rating 

The final step is to rate each security risk to enable prioritization. Use the DREAD model and score each risk on the five aspects below, using integer values 1–3 (where 1 = lowest, 3 = highest)

- Damage Potential — How severe would the impact be if the attack succeeded? 1 = Low, 2 = Medium, 3 = High
- Reproducibility — How easy is the attack to reproduce reliably? 1 = Difficult, 2 = Medium, 3 = Easy
- Exploitability — How easy is it to carry out the attack (time, skill, tools required)? 1 = Difficult, 2 = Medium, 3 = Easy
- Affected Users — How many users would be impacted if the risk materializes? 1 = Few, 2 = Some, 3 = All
- Discoverability — How easy is it for an attacker to discover the vulnerability or attack vector? 1 = Difficult, 2 = Medium, 3 = Easy

It is important to note that this process is not inherently repeatable. Different evaluators may reach different conclusions, and even the same evaluator might produce different results on different days. For this reason, justification for each rating may be required to ensure transparency and traceability.

The final score for each risk is the sum of the ratings for Damage Potential, Reproducibility, Exploitability, Affected Users, and Discoverability. Risks with higher total scores should be prioritized for mitigation

The outcome of the risk rating process is a matrix linking each risk to its severity, providing a clear view of priorities:

| Risk Id  | D     | R     | E     | A     | D     | Severity           |
| -------- | ----- | ----- | ----- | ----- | ----- | ------------------ |
| _Risk 1_ | _x1_  | _x2_  | _x3_  | _x4_  | _x5_  | = _x1+x2+x3+x4+x5_ |
| _Risk 2_ | ...   |       |       |       |       |                    |
| ...      |       |       |       |       |       |                    |

---

# Phase II : Security Requirements 

The Security Requirements goal is to identify how the security risks identified will be controlled. The security requirements definition is composed by the following
steps:

1. Constraints identification
2. Security requirements description

---

## Constraint identification 

