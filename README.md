# Salesforce to Databricks Migration & Continuous Load Requirements

This template can be copied into a Confluence page.  It provides a structure for documenting the migration of data from Salesforce to Databricks and the ongoing, continuous‑load processes.  It contains anchors and links so that the object index at the top of the page takes readers directly to the relevant section for each Salesforce object.  Replace the placeholder text, object names and field details with your own content.

## 1 Overview

* **Purpose of the migration:** Describe why data is being migrated from Salesforce to Databricks (for example, analytics, machine learning, unified reporting, etc.).
* **Scope:** Summarise which Salesforce organisation(s) and Databricks workspace(s) are in scope, any exclusions and high‑level timelines.
* **Stakeholders:** List key stakeholders such as project sponsors, data engineers, administrators and business users.
* **Assumptions and dependencies:** Note any system dependencies, required integrations or assumptions (for example, Salesforce API limits, network connectivity, identity and access management, etc.).

## 2 Object index

The table below provides quick links to each object’s migration details.  Confluence’s anchor macro is used in each section so that selecting the link jumps directly to the appropriate heading.  Replace `Object 1` … `Object 16` with your actual Salesforce object names.

| Salesforce object | Link to section |
|---|---|
| **Object 1** | [Object 1 mapping](#object1) |
| **Object 2** | [Object 2 mapping](#object2) |
| **Object 3** | [Object 3 mapping](#object3) |
| **Object 4** | [Object 4 mapping](#object4) |
| **Object 5** | [Object 5 mapping](#object5) |
| **Object 6** | [Object 6 mapping](#object6) |
| **Object 7** | [Object 7 mapping](#object7) |
| **Object 8** | [Object 8 mapping](#object8) |
| **Object 9** | [Object 9 mapping](#object9) |
| **Object 10** | [Object 10 mapping](#object10) |
| **Object 11** | [Object 11 mapping](#object11) |
| **Object 12** | [Object 12 mapping](#object12) |
| **Object 13** | [Object 13 mapping](#object13) |
| **Object 14** | [Object 14 mapping](#object14) |
| **Object 15** | [Object 15 mapping](#object15) |
| **Object 16** | [Object 16 mapping](#object16) |

## 3 Continuous load requirements

Describe the strategy for keeping the Databricks data lake/table synchronised with Salesforce once the initial migration is complete.  Include the following items:

* **Load frequency:** Specify how often the pipeline runs (for example, hourly, daily, near‑real‑time).  Note any considerations around Salesforce API limits or Databricks job scheduling.
* **Incremental logic:** Explain how incremental updates are identified (e.g. using `SystemModstamp`, `LastModifiedDate` or Change Data Capture events).  Clarify if deletes are handled via soft‑deletes or full refreshes.
* **Monitoring and alerting:** Define how data pipeline health is monitored (metrics, logs, dashboards) and who receives notifications on failures.
* **Error handling and retries:** Describe retry logic and how partial failures are reconciled.
* **Data quality checks:** List validations applied during load (duplicate detection, data type enforcement, required fields, etc.).
* **Security and compliance:** Note any encryption, anonymisation or compliance requirements that must be maintained during continuous loads.

---

## 4 Field mapping sections

Each subsection below documents a Salesforce object that will be migrated to Databricks.  At the top of each subsection there is an anchor macro (e.g. `{anchor:object1}`), which defines a bookmark.  The links in the *Object index* table above reference these anchors.  Replace the placeholder object names (`Object 1`) and field names (`Field 1`…`Field 15`) with your specific details.  For each field, capture the source and target names, data types, any transformation logic and relevant notes.

### 4.1 Object 1 mapping

{anchor:object1}

**Salesforce object:** Object 1 – *replace with actual name*

**Description:** Provide a short description of what the object represents and why it is included in the migration.

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** Describe how unique identifiers (for example `Id` or external keys) are handled in Databricks.
* **Initial load method:** Indicate whether a full extract or a filtered extract is used and any query filters applied.
* **Dependencies:** Mention dependencies on other objects (e.g. lookup relationships, foreign keys) that impact the load order.

---

### 4.2 Object 2 mapping

{anchor:object2}

**Salesforce object:** Object 2 – *replace with actual name*

**Description:** Provide a short description of what the object represents and why it is included in the migration.

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.3 Object 3 mapping

{anchor:object3}

**Salesforce object:** Object 3 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.4 Object 4 mapping

{anchor:object4}

**Salesforce object:** Object 4 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.5 Object 5 mapping

{anchor:object5}

**Salesforce object:** Object 5 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.6 Object 6 mapping

{anchor:object6}

**Salesforce object:** Object 6 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.7 Object 7 mapping

{anchor:object7}

**Salesforce object:** Object 7 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.8 Object 8 mapping

{anchor:object8}

**Salesforce object:** Object 8 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.9 Object 9 mapping

{anchor:object9}

**Salesforce object:** Object 9 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.10 Object 10 mapping

{anchor:object10}

**Salesforce object:** Object 10 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.11 Object 11 mapping

{anchor:object11}

**Salesforce object:** Object 11 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.12 Object 12 mapping

{anchor:object12}

**Salesforce object:** Object 12 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.13 Object 13 mapping

{anchor:object13}

**Salesforce object:** Object 13 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.14 Object 14 mapping

{anchor:object14}

**Salesforce object:** Object 14 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.15 Object 15 mapping

{anchor:object15}

**Salesforce object:** Object 15 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

### 4.16 Object 16 mapping

{anchor:object16}

**Salesforce object:** Object 16 – *replace with actual name*

**Description:** …

#### Field mapping

| # | Salesforce field | Salesforce data type | Databricks field | Databricks data type | Transformation / notes |
|---|---|---|---|---|---|
| 1 | Field 1 |  |  |  |  |
| 2 | Field 2 |  |  |  |  |
| 3 | Field 3 |  |  |  |  |
| 4 | Field 4 |  |  |  |  |
| 5 | Field 5 |  |  |  |  |
| 6 | Field 6 |  |  |  |  |
| 7 | Field 7 |  |  |  |  |
| 8 | Field 8 |  |  |  |  |
| 9 | Field 9 |  |  |  |  |
| 10 | Field 10 |  |  |  |  |
| 11 | Field 11 |  |  |  |  |
| 12 | Field 12 |  |  |  |  |
| 13 | Field 13 |  |  |  |  |
| 14 | Field 14 |  |  |  |  |
| 15 | Field 15 |  |  |  |  |

#### Migration and load notes

* **Primary key mapping:** …
* **Initial load method:** …
* **Dependencies:** …

---

## 5 Additional considerations

* **Testing and validation:** Before production cutover, perform data reconciliation between Salesforce and Databricks to ensure the field mappings work as expected.  Validate record counts, data types and transformation logic.
* **Cut‑over strategy:** Decide whether you will run a dual‑write period, freeze writes during the cut‑over or use another approach.
* **Change management:** Identify any user training, documentation updates or downstream report modifications required due to the migration.
