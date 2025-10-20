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

## Asset Profiling

Each Asset has its own characteristics and nature. Assets may be vulnerable to Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege

The outcome of the Asset Profiling phase is a matrix mapping Assets against STRIDE categories.
This matrix identifies whether Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service (DoS), or Elevation of Privilege affecting each asset could result in a cybersecurity risk

| Asset Id | Is Spoofing a risk? | Is Tampering a risk? | Is Repudiation a risk? | Is Disclosure a risk? | Is DoS a risk? | Is Elevation a risk? |
| -------- | ------------------- | -------------------- | ---------------------- | --------------------- | -------------- | -------------------- |
| _Asset 1_     | _Yes/No_       |                      |                        |                       |                |                      |
| _Asset 2_     | ...            |                      |                        |                       |                |                      |
| ...           |                |                      |                        |                       |                |                      |
