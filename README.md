
# **Project Approach: Local AI LLM for PDF Extraction, Summary, and Assignment Support**  
**Student:** Harshada Deshmukh, Janhavi Desale, Rohini Jadhav 


## 1. What Is This Project About?

This project is about using **AI that runs on my own computer** (local AI) instead of sending documents to the cloud. I want to build a system where teachers can upload a PDF (like study material or a textbook chapter), and the AI will automatically:

- Extract all the text from the PDF
- Create a simple summary
- Pull out important keywords
- Suggest possible assignment topics



## 2. What I Will Study and Research

### 2.1 Local AI Tools to Compare

I will research and compare these popular local LLM options:

| Tool | What It Is | Good For | Requirements |
|------|------------|----------|--------------|
| **Ollama** | Easy tool to run LLMs locally on PC/Mac | Students, beginners | 8GB+ RAM, decent GPU |
| **LM Studio** | Desktop app with nice interface for local models | Easy testing, no coding | Windows/Mac, 8GB RAM |
| **GPT4All** | Open-source local AI that works offline | Privacy-focused users | 8GB RAM minimum |
| **Llama.cpp** | Lightweight tool for running LLMs | Low hardware requirements | 4GB+ RAM |

### 2.2 PDF Text Extraction Methods

I will study how to pull text from PDFs:

- **PyPDF2** – Simple Python library for basic PDFs
- **PyMuPDF** – Faster and handles more PDF types
- **Layout detection** – For PDFs with images and tables (more advanced)

### 2.3 Privacy Benefits

Why use local AI instead of cloud AI (like ChatGPT)?

| Benefit | Explanation |
|---------|-------------|
| **No data leaves my computer** | Student/teacher documents stay private |
| **No internet needed** | Works offline, good for areas with poor connectivity |
| **No subscription fees** | Free open-source tools, no monthly payments |
| **Full control** | I can modify the system however I want |
| **No usage limits** | Can process as many PDFs as I want |

***

## 3. How the System Will Work (Simple Workflow)

**Step 1:** Teacher uploads a PDF file (like a chapter from a textbook)

**Step 2:** System extracts all the text from the PDF pages

**Step 3:** Text is sent to the local AI model running on the computer

**Step 4:** AI creates these outputs:
- A short summary (3–5 sentences)
- A longer summary (1 paragraph)
- List of 5–10 important keywords
- 3–5 possible assignment questions/topics

**Step 5:** Teacher downloads or copies the results

**Step 6:** If the local AI is too slow or computer is weak, fall back to a simpler model or cloud option (backup plan)

***

## 4. Sample Output Format (What the Summary Will Look Like)

```
========================================
PDF SUMMARY REPORT
========================================

File Name: Chapter_5_Biology.pdf
Pages Processed: 12
Processing Time: 45 seconds

----------------------------------------
SHORT SUMMARY (3–5 sentences)
----------------------------------------
This chapter explains the structure and function of plant cells. 
It covers cell organelles like chloroplasts, mitochondria, and 
nucleus. The chapter also discusses photosynthesis and how plants 
make their own food using sunlight.

----------------------------------------
LONG SUMMARY (1 paragraph)
----------------------------------------
Chapter 5 introduces students to plant cell biology. It begins 
with the basic definition of a cell and then moves into detailed 
explanations of each organelle. Special focus is given to 
chloroplasts and the process of photosynthesis. The chapter 
includes diagrams showing cell structure and comparison tables 
between plant and animal cells.

----------------------------------------
KEYWORDS (5–10 important terms)
----------------------------------------
1. Plant Cell
2. Chloroplast
3. Mitochondria
4. Photosynthesis
5. Cell Wall
6. Nucleus
7. Cytoplasm
8. Cell Membrane
9. Chlorophyll
10. Energy Production

----------------------------------------
POSSIBLE ASSIGNMENT TOPICS
----------------------------------------
1. Draw and label a plant cell with all organelles
2. Explain photosynthesis in your own words (200 words)
3. Compare plant cell vs animal cell (table format)
4. What would happen if chloroplasts stopped working?
5. Research project: How do plants produce oxygen?

========================================
```

***

## 5. Hardware Requirements (What Computer Do I Need?)

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| **RAM** | 8 GB | 16 GB or more |
| **Processor** | Intel i5 / AMD Ryzen 5 | Intel i7 / AMD Ryzen 7 |
| **Graphics Card** | Integrated GPU | Dedicated GPU (NVIDIA GTX 1650+) |
| **Storage** | 10 GB free space | 20 GB free space (for models) |
| **Operating System** | Windows 10 / macOS / Linux | Windows 11 / macOS |


## 6. Limitations and Challenges

| Limitation | What It Means | How I Will Handle It |
|------------|---------------|---------------------|
| **Slower than cloud AI** | Local AI takes more time to process | Use smaller models, be patient |
| **Needs good hardware** | Weak computers may struggle | Offer multiple model sizes (small/medium/large) |
| **Model quality varies** | Some free models are not as smart | Test multiple models, pick the best one |
| **Large PDFs are hard** | Very long documents may not fit in memory | Split PDF into smaller sections |
| **Complex PDFs** | Scanned PDFs or images inside PDFs need special tools | Use OCR (optical character recognition) for scanned files |

***

## 7. Fallback Options (Plan B)

If the local AI does not work well, I have these backup plans:

1. **Use a smaller AI model** – Faster but less accurate
2. **Split PDF into smaller parts** – Process page by page instead of whole document
3. **Use cloud AI as backup** – Only if user agrees and data is not sensitive
4. **Simplify the output** – Just summary without keywords or assignment topics

***

## 8. Backend API Integration Notes

If the company wants to connect this to their existing system:

- The local AI runs as a **separate service** on the computer
- Backend sends PDF to local AI using **REST API** (simple HTTP requests)
- Local AI returns JSON format with summary, keywords, and topics
- Can work with **Python Flask** or **FastAPI** for the backend
- No internet needed for the AI part, only for user login if needed

**Simple API structure:**
```
POST /summarize
Body: { "file": "PDF file here" }
Response: { "summary": "...", "keywords": [...], "assignment_topics": [...] }
```

***

## 9. What I Will Submit (Deliverables)

| Deliverable | What It Is |
|-------------|------------|
| **Workflow description** | Simple written explanation of how the system works (this document) |
| **Sample summary output** | Example of what the AI summary will look like (shown above) |
| **Local AI tool comparison** | Table comparing Ollama, LM Studio, GPT4All, Llama.cpp |
| **Integration notes** | Simple explanation of how to connect to backend APIs |

***

## 10. What I Will Learn From This Project

- How to run AI models on my own computer (no cloud needed)
- How to extract text from PDF files
- How AI can summarize long documents
- Why privacy matters in educational technology
- How to build a useful tool for teachers and students

***

## 11. Simple Summary

| Aspect | Details |
|--------|---------|
| **Goal** | Build a private AI system that summarizes PDFs for teachers |
| **Key Feature** | Everything runs locally – no internet, no data shared |
| **Outputs** | Summary, keywords, assignment topics |
| **Tools** | Ollama or LM Studio for AI, PyPDF2 for PDF extraction |
| **Hardware** | 8GB+ RAM computer (works on most student laptops) |
| **Privacy** | 100% private – documents never leave the computer |

**Conclusion:** This is a simple, private, free tool that helps teachers turn PDFs into summaries and assignment ideas without sending data to the cloud.
