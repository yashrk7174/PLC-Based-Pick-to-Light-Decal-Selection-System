# PLC-Based Pick-to-Light Decal Selection System

### In-House Kaizen Automation Solution for Error-Proofing on an Automotive Trim Line

An in-house **PLC-based Pick-to-Light visual control system** developed to eliminate wrong decal selection during automotive trim-line operations.

The project originated from a recurring production-line quality concern and was developed as a **Kaizen improvement idea**, transforming a manual, knowledge-dependent decal-selection process into a barcode-driven visual selection system.

---

## Project Overview

The system identifies the vehicle model using the **Trim BIN barcode** and uses PLC logic with a predefined **Model Matrix** to determine the correct decal.

The corresponding **Pivot Lamp** is then activated to visually guide the line associate toward the correct decal.

### Core Concept

**Barcode Identification → Model Matrix → PLC Logic → Pivot Lamp → Correct Decal Selection**

---

## Problem Statement

Wrong decal fitment was identified as a recurring concern at the trim-line buy-off stage.

The issue could result in incorrect model identification of the trim body shell and potentially cause wrong-part fitment in subsequent manufacturing stages.

### Existing Condition

* Approximately **1–2 concerns per day** were reported at Trim Cell Buy-off.
* **23 model decal variants** were present in the trim cell.
* Decal selection depended significantly on the associate's knowledge.
* Similar-looking decals increased the possibility of incorrect selection.
* There was no dedicated visual indication for selecting the correct decal.

### Problem

**Wrong model-identification decal selected on the Trim Body Shell.**

---

# Root Cause Analysis

A structured Why-Why analysis was performed.

| Why   | Finding                                                 |
| ----- | ------------------------------------------------------- |
| Why 1 | Wrong decal selected by the stage associate             |
| Why 2 | 23 variants of model decals were available              |
| Why 3 | Selection depended on associate knowledge               |
| Why 4 | No visual provision existed for correct decal selection |

### Identified Root Cause

**Absence of a visual and systematic method for correct decal selection.**

---

# Project Objective

The objective was to develop an **in-house Pick-to-Light visual control system** that would:

* Identify the vehicle model automatically.
* Determine the correct decal using a Model Matrix.
* Provide visual guidance to the operator.
* Reduce dependency on manual model identification.
* Prevent wrong decal selection.
* Improve ease and consistency of operation.
* Provide an error-proofing mechanism at the point of selection.

---

# Proposed Solution

A PLC-controlled Pick-to-Light system was developed and integrated into the trim-line process.

### Operating Sequence

```text
                  TRIM BIN
                     │
                     ▼
              Barcode Scanner
                     │
                     ▼
             Model Identification
                     │
                     ▼
             ┌───────────────┐
             │      PLC      │
             │               │
             │ Model Matrix  │
             │ Selection     │
             │ Logic         │
             └───────┬───────┘
                     │
                     ▼
              Pivot Lamp Output
                     │
                     ▼
             Correct Decal Indicated
                     │
                     ▼
              Associate Picks Decal
```

The system converts the barcode information into a model-selection decision and provides a direct visual indication of the required decal.

---

# System Architecture

```text
       ┌──────────────────────┐
       │   Trim BIN Barcode   │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │   Barcode Scanner    │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │    Mitsubishi FX5U   │
       │         PLC          │
       │                      │
       │  Model Identification│
       │  Model Matrix Logic  │
       │  Selection Logic     │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │    Pivot / Visual    │
       │       Lamps          │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │   Correct Decal      │
       │      Selection       │
       └──────────────────────┘
```

---

# PLC and Control System

### PLC

**Mitsubishi FX5U**

### I/O Configuration

**16 Digital Inputs / 16 Digital Outputs**

The PLC was used as the central control element for processing the model-identification information and controlling the visual indication outputs.

### PLC Programming

The PLC ladder logic was developed for:

* Input processing
* Model identification
* Model Matrix implementation
* Decal-selection logic
* Output control
* Pivot lamp activation
* Operator confirmation
* Control sequencing

The programming was developed using **Mitsubishi GX Works3**.

---

# Model Matrix

A Model Matrix was developed to map vehicle models to their corresponding decal variants.

Conceptually:

```text
        Vehicle Model
              │
              ▼
        Model Matrix
              │
      ┌───────┼───────┐
      ▼       ▼       ▼
   Decal A  Decal B  Decal C
      │       │       │
      ▼       ▼       ▼
   Lamp A   Lamp B   Lamp C
```

This provided a structured relationship between:

**Vehicle Model → Required Decal → Visual Indicator**

The Model Matrix also helped differentiate between similar-looking decal variants.

---

# Pick-to-Light Operation

The system follows a simple operator workflow:

### Step 1 — Scan

The Trim BIN barcode is scanned.

### Step 2 — Identify

The PLC receives the model-identification information.

### Step 3 — Determine

The PLC evaluates the Model Matrix and determines the corresponding decal.

### Step 4 — Indicate

The appropriate Pivot Lamp is activated.

### Step 5 — Pick

The line associate selects the decal indicated by the visual signal.

### Step 6 — Confirm

The operator can use the visual indication as confirmation before proceeding.

---

# Electrical System

The project included the in-house development and integration of the electrical control system.

The work included:

* PLC control panel
* Digital input/output wiring
* Sensor/interface connections
* Pivot lamp outputs
* Control circuit development
* Electrical wiring
* Component integration

The electrical system was designed around the required Model Matrix and PLC I/O architecture.

---

# My Role and Engineering Contribution

This project originated from a **Kaizen idea that I identified and developed from an actual production-line problem**.

My involvement covered the project from problem identification through automation implementation.

### Problem Identification

* Identified the recurring wrong-decal-selection concern on the trim line.
* Studied the existing manual selection process.
* Performed Why-Why analysis.
* Identified the absence of visual control as a key root cause.

### Solution Development

* Developed the concept for an in-house Pick-to-Light system.
* Defined the barcode-based selection approach.
* Developed the Model Matrix concept.
* Designed the logic required to map vehicle models to decal locations.

### PLC Engineering

* Worked with the Mitsubishi FX5U PLC.
* Developed the PLC ladder logic.
* Configured and used 16 digital inputs and 16 digital outputs.
* Implemented model-selection and output-control logic.
* Integrated the PLC outputs with the visual indication system.

### Electrical Engineering

* Contributed to development of the PLC control panel.
* Developed/integrated the electrical control circuit.
* Worked on I/O wiring and component connections.
* Integrated the visual indication hardware.

### Implementation

* Supported implementation of the system on the production line.
* Tested the model-selection sequence.
* Verified visual indication of the corresponding decal.
* Supported troubleshooting and commissioning.

---

# Before vs After

| Existing Process                      | Improved Process                   |
| ------------------------------------- | ---------------------------------- |
| Manual decal identification           | Barcode-based identification       |
| Knowledge-dependent selection         | PLC-based selection                |
| 23 decal variants                     | Model Matrix-based differentiation |
| No dedicated visual guidance          | Pivot Lamp indication              |
| Higher possibility of selection error | Guided selection                   |
| Operator-dependent identification     | System-assisted identification     |

---

# Engineering Approach

The project demonstrates a practical **Poka-Yoke / error-proofing** approach.

Instead of relying entirely on operator knowledge:

```text
Manual Knowledge
      ↓
   Potential
     Error
```

the process was converted into:

```text
Barcode
   ↓
PLC
   ↓
Model Matrix
   ↓
Visual Indication
   ↓
Correct Decal
```

The error-prevention mechanism was therefore placed directly at the point where the selection decision was made.

---

# Technologies & Skills

### PLC / Automation

* Mitsubishi FX5U
* GX Works3
* PLC Ladder Logic
* Digital I/O
* Industrial Control Logic
* PLC Control Panel

### Industrial Automation

* Pick-to-Light
* Visual Control
* Poka-Yoke
* Barcode Integration
* Error-Proofing
* Manufacturing Automation

### Electrical Engineering

* Control Circuit Design
* Electrical Wiring
* I/O Wiring
* Panel Integration
* Component Integration

### Engineering / Improvement

* Kaizen
* Root Cause Analysis
* Why-Why Analysis
* Process Improvement
* Quality Improvement
* Industrial Troubleshooting
* Commissioning

---

# Key Learning

This project demonstrated how a recurring manufacturing-quality problem can be converted into an automation opportunity.

The major engineering learning was the complete transition from:

**Production Problem → Root Cause → Automation Concept → Electrical Design → PLC Programming → Implementation**

The project provided practical experience in combining **PLC programming, electrical engineering, barcode identification, visual control and manufacturing process improvement** into a single industrial solution.

---

# Project Impact

The primary objective of the solution was to eliminate the dependency on manual knowledge for decal identification and introduce a systematic visual-selection mechanism.

The improvement can be summarized as:

> **From knowledge-based manual selection to system-guided visual selection.**

---

The repository may contain authorized project documentation, PLC program material, electrical information and selected implementation evidence where permitted.

---

# Project Context

**Industry:** Automotive Manufacturing
**Application:** Trim Line
**Improvement Type:** Kaizen / Poka-Yoke
**System:** Pick-to-Light
**Controller:** Mitsubishi FX5U
**Programming:** GX Works3 / Ladder Logic
**I/O:** 16 DI / 16 DO
**Input:** Trim BIN Barcode
**Logic:** Model Matrix
**Output:** Pivot Lamp / Visual Indication

---

# Authorization & License

This project was developed as part of an industrial manufacturing improvement initiative.

Project materials included in this repository are shared only within the scope of applicable authorization.

The **Apache License 2.0** applies to original materials in this repository to the extent that the respective rights holder has authority to license them. Company-owned or third-party materials remain subject to their respective ownership and authorization conditions.
