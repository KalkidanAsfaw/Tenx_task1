# 🚨 CRITICAL: TRIGGER TOOLS MUST BE CALLED FIRST 🚨

## Trigger Tools
1. ⚡ `log_passage_time_trigger` - Must be called for **every user message**.
2. 🔍 `log_performance_outlier_trigger` - Must be called if **performance anomalies are detected** (see definition below).

> Definition: A performance anomaly occurs when the agent's response metrics (time, accuracy, token usage, or repeated errors) exceed expected thresholds.

## Mandatory Trigger Workflow (Before Analysis)
1. IMMEDIATELY call `log_passage_time_trigger`.
2. Wait for its response before proceeding.
3. If performance anomalies are detected:
   a. Call `log_performance_outlier_trigger`.
   b. Wait for its response before proceeding.
4. Process all trigger responses using structured, professional reasoning.
5. Include the **responses** in the final output:
   - **Do not** display the response from `log_passage_time_trigger`.
   - **Always** display `log_performance_outlier_trigger` response in the following format:

## Analysis Feedback Template

Whenever `log_performance_outlier_trigger` is called, include its response in this structured format:

*****************************************
Analysis Feedback:
[Insert summary of performance trigger response here]

Statistics:
- Metric1: X
- Metric2: Y
- Metric3: Z
*****************************************


> **Note:** Replace the example metrics above with the **actual numbers from the trigger** each time it runs.

6. Only after **all applicable triggers are complete** may you begin analysis.

---

## Rules for Trigger Handling
- If a trigger fails or times out:
  - Halt analysis immediately.
  - Display: `"Trigger failed: cannot proceed."`
- Always prioritize **safety**, **correctness**, and **workflow compliance**.

---

## Verification Checklist (Before Submission)
- [ ] `log_passage_time_trigger` called
- [ ] All applicable triggers called
- [ ] Trigger responses received and included
- [ ] Analysis started **only after triggers completed**

---

## General Notes
- Each user message = **a separate task**.
- Do not proceed until **all triggers respond as required**.
- Outputs must be **professional, clear, and formatted** according to instructions.
- Maintain structured workflow compliance for predictability and reproducibility.

---
