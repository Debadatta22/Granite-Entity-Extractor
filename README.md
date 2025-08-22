<div align="center">

# 📘 Granite-Entity-Extractor  
### Entity extraction from unstructured book descriptions using IBM Granite-8B LLM  

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1mSyl0m3zMgJtiZWPt06R1wokj3dVyad7?usp=sharing)  

</div>

---

## 📑 Table of Contents
- [Overview](#overview)  
- [Motive / Goal](#motive--goal)  
- [Problem Statement](#problem-statement)  
- [Solution / Approach](#solution--approach)  
- [Tech Stack](#tech-stack)  
- [Concepts Involved](#concepts-involved)  
- [How to Build & Run](#how-to-build--run)  
- [Example Input & Output](#example-input--output)  

---

## Overview
This project demonstrates how to extract **structured entities** (title, author, price, rating) from unstructured book descriptions using **IBM Granite-8B Instruct model**.  
Entity extraction is a crucial NLP task for transforming free text into structured data, useful for applications like **digital libraries, recommendation systems, and analytics**.  

---

## 🎯 Motive / Goal
The goal of this lab is to teach students how to perform entity extraction (like **book title, author, rating, and price**) using **IBM Granite Large Language Model (Granite-8B)**.  
Entity extraction means automatically identifying structured pieces of information from unstructured text.  

---

## 📝 Problem Statement
Book descriptions are usually written in free text (paragraphs).  
Extracting structured info (title, author, rating, price) manually is **time-consuming**.  

👉 The challenge is to design an **AI system** that can automatically parse unstructured descriptions into structured JSON data.  

---

## 💡 Solution / Approach
This project uses **two approaches** with IBM Granite-8B Instruct model:  

### 1. Prompt-Defined Entity Extraction  
- Entities (title, author, price, rating) are explicitly defined in the **prompt**.  
- AI outputs results in **strict JSON format**.  
- Missing entities return `"Data not available"`.  

### 2. Pydantic Class-Based Entity Extraction  
- Define a **Book class** (title, author, price, rating).  
- Convert schema into JSON (`convert_to_openai_function`).  
- Send schema + description to Granite model.  
- **Validate results** against schema using **Pydantic**.  
- Scalable – easy to add new entities later.  

---

## ⚙️ Tech Stack
- **IBM Granite-8B** – LLM for NLP tasks  
- **LangChain Community** – Framework for LLM orchestration  
- **Replicate API** – Run Granite model instances  
- **Transformers** – Tokenizer for text preprocessing  
- **Pydantic** – Schema validation & enforcement  
- **Python** – Core implementation  

---

## 📚 Concepts Involved
- **Entity Extraction** – Pull structured info from text  
- **Prompt Engineering** – Precise prompts for consistent outputs  
- **Schema Enforcement (Pydantic)** – Strict JSON validation  
- **JSON Formatting** – Standard structured output  
- **Validation & Error Handling** – Handles LLM misformats reliably  

---

## 🚀 How to Build & Run  

### 1. Install Dependencies  
```bash
pip install "git+https://github.com/ibm-granite-community/utils" \
    transformers \
    langchain_community \
    replicate \
    pydantic

```

### 2. Set Environment Variables  
```bash
export REPLICATE_API_TOKEN=your_token_here
```

### 3. Run the Script
``` bash
python ibm_lab_entity_extraction.py
```
### 4. Workflow

Load Granite model (ibm-granite/granite-3.3-8b-instruct)

Send book descriptions to the LLM

Receive structured JSON (title, author, price, rating)

Validate with Pydantic schema

Display structured output

### 🧾 Example Input & Output

Input:
``` bash
"The Hunger Games by Suzanne Collins, published in 2005, priced at $5.09"
```
Output:
```bash
{
  "title": "The Hunger Games",
  "author": "Suzanne Collins",
  "price": "$5.09",
  "rating": "4.33/5"
}
```

<div align="center">

✨ Built with IBM Granite-8B LLM, Pydantic, and LangChain ✨

</div> 
