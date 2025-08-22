# Granite-Entity-Extractor

Entity extraction from unstructured book descriptions using IBM Granite-8B LLM.
--------------------

Hands-on IBM SkillsBuild project using Granite-8B LLM in IBM watsonx.ai to extract entities like title, author, rating, and price from book descriptions. Built with Pydantic, JSON schema validation, and AI-powered text extraction.

-------------------

# 📘 Entity Extraction from Book Descriptions using IBM Granite-8B

## Overview
This project demonstrates how to extract **structured entities** (title, author, price, rating) from unstructured book descriptions using **IBM Granite-8B Instruct model**.  
Entity extraction is a crucial NLP task for transforming free text into structured data, useful for applications like digital libraries, recommendation systems, and analytics.

---

## 🎯 Objectives
- Learn to perform entity extraction using **LLMs (Granite-8B)**.
- Explore **prompt-engineering-based extraction**.
- Implement **schema-based extraction** with **Pydantic validation**.
- Generate consistent, structured JSON output.

---

## 📝 Problem Statement
Free-text book descriptions contain valuable details (title, author, price, ratings), but lack structure.  
This project builds an **AI-powered entity extractor** that converts such unstructured descriptions into structured JSON automatically.

---

## 💡 Approaches
### 1. Prompt-Defined Extraction
- Define required entities (title, author, price, rating) in the **prompt**.
- Ensure JSON-only output with `"Data not available"` for missing info.

### 2. Pydantic Class-Based Extraction
- Define a Python class (`Book`) for entity schema.
- Convert schema into JSON using `convert_to_openai_function`.
- Enforce structured output with **Pydantic validation**.
- Scalable & flexible for adding more entities.

---

## ⚙️ Tech Stack
- **IBM Granite-8B** – LLM for NLP tasks
- **LangChain Community** – LLM orchestration
- **Replicate API** – Model execution
- **Transformers** – Tokenization
- **Pydantic** – Schema validation
- **Python** – Implementation

---

## 🚀 Running the Project

### 1. Install Dependencies
```bash
pip install "git+https://github.com/ibm-granite-community/utils" \
    transformers \
    langchain_community \
    replicate \
    pydantic
