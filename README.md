# REU_TARA

# Automated Threat Analysis and Risk Assessment Using Multi-Modal Deep Learning and Retrieval-Augmented LLMs

## Problem Statement
ISO/SAE 21434 requires a Threat Analysis and Risk Assessment (TARA) for
automotive systems. Doing it by hand is slow, inconsistent and depends
heavily on expert effort. This project automates TARA generation from a
system architecture diagram.

## Objectives
- Extract components and interfaces automatically from architecture diagrams
  using a vision-language model
- Retrieve relevant threats and mitigations from a knowledge base using RAG
- Generate structured, ISO 21434-compliant TARA rows
- Validate the output against published case-study findings

## Team Members
| Name | Role |
|------|------|
| Shrusti | [role, e.g. Developer / Team representative] |
| [Name] | [role] |
| [RA / Mentor] | Concerned RA |

## Technologies / Tools Used
- Python, Google Colab
- Gemini 2.5-flash (vision extraction and TARA generation)
- ChromaDB with all-MiniLM-L6-v2 embeddings (retrieval)
- NetworkX
- FastAPI / Streamlit (deployment)

## Pipeline
1. **Stage 1:** Gemini vision extracts components and interfaces from the architecture diagram
2. **Stage 2:** ChromaDB retrieval over a threat and mitigation corpus
3. **Stage 3:** Gemini generates TARA rows as JSON, using an explicit ISO 21434 risk matrix in the prompt

## Current Progress (as of 23 Nov 2026)
- [✓] End-to-end pipeline working on Google Colab
- [✓] Case study: TPMS (7 components, 21-chunk corpus). 6/6 coverage vs Xu et al., 100% format compliance, 100% groundedness
- [✓] Case study: BCM Car A (6 components, 30-chunk corpus). 5/5 coverage vs DefenseWeaver
- [✓] Expected vs Generated comparison table
- [✓] BCM Car B: Stage 1 extracted, TARA run pending
- [✓] FastAPI/Streamlit deployment
- [✓] Final report

## Repository Structure
- `notebooks/`: Colab pipeline
- `data/`: threat/mitigation corpus, sample diagrams
- `results/`: generated TARA outputs and evaluation tables

## How to Run
1. Open the notebook in Google Colab
2. Add your Gemini API key to Colab secrets
3. Run all cells
