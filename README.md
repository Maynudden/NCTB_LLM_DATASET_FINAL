# NCTB LLM Dataset — Classes 3–10

## 1. Overview

This dataset contains OCR-processed and structured educational content from NCTB Bangladesh textbooks covering Classes 3 through Class 10.

Class 9 and Class 10 textbooks are represented jointly as `Class 9 & 10`.

---

## 2. Dataset Coverage

| Class | Records |
|---|---:|
| Class 3 | 1,110 |
| Class 4 | 1,111 |
| Class 5 | 1,205 |
| Class 6 | 2,098 |
| Class 7 | 2,417 |
| Class 8 | 2,875 |
| Class 9 & 10 | 3,802 |
| **Total** | **14,618** |

---

## 3. Main Dataset

The primary combined dataset is:

`NCTB_LLM_Master_Dataset.jsonl`

Total records: **14,618**

The Master Dataset contains a globally unique `master_id` for every record.

---

## 4. Dataset Format

The dataset uses JSON Lines (`.jsonl`) format.

Each line represents one page-level record.

Example:

```json
{
  "master_id": "nctb_class_3_0000001",
  "original_id": "class3_bangla_00001",
  "id": "class3_bangla_00001",
  "grade": "Class 3",
  "class": "3",
  "subject": "Bangla",
  "book": "NCTB Bangla",
  "source": "NCTB Bangladesh",
  "curriculum": "NCTB Curriculum",
  "language": "Bangla",
  "page": 1,
  "content": "Textbook content..."
}
```

---

## 5. Field Description

### master_id

Globally unique identifier created for the Master Dataset.

### original_id

Identifier from the original class-wise dataset.

### id

Original record identifier.

### grade

Class or grade group of the textbook.

### class

Class identifier.

### subject

Subject associated with the record.

### book

Name of the source textbook or PDF.

### source

Source organization.

Value: `NCTB Bangladesh`

### curriculum

Curriculum designation.

Value: `NCTB Curriculum`

### language

Language metadata associated with the textbook.

### page

Source PDF page number.

### content

OCR/extracted textbook content.

---

## 6. Folder Structure

The final package contains:

```text
NCTB_LLM_DATASET_FINAL/
|
|-- README.md
|
|-- NCTB_LLM_Master_Dataset.jsonl
|
|-- Class_3/
|   `-- subject-wise JSONL files
|
|-- Class_4/
|   `-- subject-wise JSONL files
|
|-- Class_5/
|   `-- subject-wise JSONL files
|
|-- Class_6/
|   `-- subject-wise JSONL files
|
|-- Class_7/
|   `-- subject-wise JSONL files
|
|-- Class_8/
|   `-- subject-wise JSONL files
|
`-- Class_9_10/
    `-- subject-wise JSONL files
```

---

## 7. Processing Pipeline

The dataset processing pipeline included:

1. PDF collection
2. PDF text-layer detection
3. OCR where required
4. OCR cleaning
5. Duplicate/removal checks
6. Book-level record counting
7. Identification of problematic text-layer PDFs
8. Forced OCR for problematic books
9. OCR merge
10. Subject-wise splitting
11. Metadata generation
12. Class-wise validation
13. Master dataset construction
14. Master dataset validation
15. Final package creation

---

## 8. Validation Results

The final Master Dataset was structurally validated.

- Total records: **14,618**
- Expected records: **14,618**
- Unique master IDs: **14,618**
- Duplicate master IDs: **0**
- Missing master IDs: **0**
- Missing original IDs: **0**
- Invalid JSON records: **0**
- Empty content records: **0**
- Missing page records: **0**
- Missing required fields: **0**
- Class-wise counts: **All matched expected counts**
- Final Master Validation: **PASSED**

---

## 9. Class-wise Validation

| Class | Records |
|---|---:|
| Class 3 | 1,110 |
| Class 4 | 1,111 |
| Class 5 | 1,205 |
| Class 6 | 2,098 |
| Class 7 | 2,417 |
| Class 8 | 2,875 |
| Class 9 & 10 | 3,802 |

---

## 10. OCR Note

The dataset contains OCR-derived text for pages where OCR was required.

Structural validation confirms JSONL validity, required metadata presence, record counts, unique Master IDs, page availability, and non-empty content.

Structural validation does not mean that every OCR character has been manually verified against the original textbook page.

OCR text may therefore contain recognition errors, especially for complex layouts, mathematical notation, tables, diagrams, or unusual typography.

---

## 11. Intended Uses

The dataset can be used for research and development involving:

- NCTB educational question answering
- Educational chatbots
- Retrieval-Augmented Generation (RAG)
- Text retrieval
- Embedding generation
- Vector database experiments
- Question answering systems
- Dataset analysis
- LLM-related research

---

## 12. Further Processing for LLM/RAG

The dataset is structurally ready for downstream research.

Depending on the project, additional processing may be required, such as:

- Text normalization
- Chunking
- Train/validation/test splitting
- Embedding generation
- Vector database indexing
- Retrieval configuration
- RAG pipeline construction

---

## 13. Source

Source material: NCTB Bangladesh textbooks.

---

## 14. Dataset Version

NCTB LLM Dataset — Classes 3–10

Final validated package.

Total records: **14,618**

---

## 15. Important Note

This package is intended for research and educational development.

The presence of OCR-derived content means that downstream systems should be evaluated for OCR-related errors before deployment in high-accuracy applications.