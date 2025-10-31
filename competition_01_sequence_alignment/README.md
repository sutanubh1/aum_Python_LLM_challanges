# 🧬 Protein Alignment Search Challenge

### Overview
You are provided with:
- A **query protein sequence** (query.fasta), and  
- A **database of ~10K protein (template) sequences** (uniprot_10k_fastas.zip).  

Your goal is to identify which template(s) best match the query sequence using sequence alignment techniques.

---

## 🧠 Task Description

### Your Task
1. **Implement:**
   - **Needleman–Wunsch (Global Alignment)**

   You may choose *one* algorithm. Your implementation must be correct, efficient, and clearly explained in your code.

2. **Compare the query with each of the 10K template sequences.**
   - Use a **similarity matrix** (provided) and Gap penalty = -5 to calculate alignment scores. 

3. **Compute the alignment score** for each query–template pair.

4. **Normalize your alignment scores by alignment length:**  
`Normalized Score = Alignment Score / Alignment Length`

5. **Measure the total computation time** required to align the **query sequence against all 10K templates**.  
   - Record this time in seconds.  
   - You may use Python’s built-in `time` or `timeit` module.

6. **Identify and report the Top 3 best-matching sequences** based on normalized scores.

---

## 📂 Input Format
- Input files are provided in **FASTA format**:
  - **query sequence**.
  - **10K template sequences**.

### 🔹 FASTA Reading Note
You **may use Biopython** to read FASTA files.  
Example:

```python
from Bio import SeqIO

query = str(next(SeqIO.parse("query.fasta", "fasta")).seq)
templates = [str(rec.seq) for rec in SeqIO.parse("templates.fasta", "fasta")]
```
---
### ⚙️ Rules and Notes
Do not use any prebuilt alignment libraries (e.g., Bio.pairwise2, Bio.Align, parasail, or SeqAlign).
You may use standard Python libraries such as numpy, pandas, matplotlib, seaborn, and csv.
Implement gap penalties explicitly (e.g., gap penalty = -5).

Include clear comments and docstrings explaining the purpose of each function and variable.
Proper normalization of scores is mandatory before ranking templates.

Your code must report the total runtime for the full query vs. all 10K templates.

---

### 🧾 Expected Output Format

The output should be a structured table that includes alignment results and runtime.

| Template ID | Raw Score | Normalized Score |
|--------------|------------|------------------|
| Template_01 | 246 | 1.92 |
| Template_45 | 230 | 1.78 |
| Template_23 | 224 | 1.72 |

At the end of the output, print the total compute time and the query-template alignment for the best-fit template only.

### Deliverables
---
Each submission must include the following files: Your final code implementation (.py or .ipynb) and the output file (.txt or .docx)

### 📊 Evaluation Components

| Component | Description | Points |
|------------|-------------|--------|
| **Algorithm Implementation** | Correct and efficient Needleman–Wunsch | **40** |
| **Handling Input Data** | Proper parsing of query and template FASTA sequences | **20** |
| **Ranking & Output Format** | Correct computation, normalization, and top matches identification | **20** |
| **Code Explanation** | Clear comments, descriptive variables, and logical structure | **10** |
| **Computation Time Measurement** | Accurate reporting of total runtime | **10** |
| **Total** | | **100 points** |
