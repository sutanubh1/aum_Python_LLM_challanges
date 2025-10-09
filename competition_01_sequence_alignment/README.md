# 🧬 Protein Alignment Search Challenge

### Overview
You are provided with:
- A **query protein sequence** (e.g., a newly discovered protein), and  
- A **database of 100 protein sequences** (template proteins).  

Your goal is to identify which template(s) best match the query sequence using sequence alignment techniques.

---

## 🧠 Task Description

### Your Task
1. **Implement either:**
   - **Needleman–Wunsch (Global Alignment)**, or  
   - **Smith–Waterman (Local Alignment)**  

   You may choose *one* algorithm. Your implementation must be correct, efficient, and clearly explained in your code.

2. **Compare the query with each of the 100 template sequences.**
   - Use a **similarity matrix** (provided) to calculate alignment scores.  

3. **Compute the alignment score** for each query–template pair.

4. **Normalize your alignment scores** by alignment length:
   \[
   \text{Normalized Score} = \frac{\text{Alignment Score}}{\text{Alignment Length}}
   \]

5. **Measure the total computation time** required to align the **query sequence against all 100 templates**.  
   - Record this time in seconds (or milliseconds).  
   - You may use Python’s built-in `time` or `timeit` module.

6. **Identify and report the Top 3 best-matching sequences** based on normalized scores.

---

## 📂 Input Format
- Input files are provided in **FASTA format**:
  - **query sequence**.
  - **100 template sequences**.

### 🔹 FASTA Reading Note
You **may use Biopython** to read FASTA files.  
Example:

```python
from Bio import SeqIO

query = str(next(SeqIO.parse("query.fasta", "fasta")).seq)
templates = [str(rec.seq) for rec in SeqIO.parse("templates.fasta", "fasta")]
```
---

### 🧾 Expected Output Format

The output should be a structured table (CSV or Markdown format) that includes alignment results and runtime.

| Template ID | Raw Score | Normalized Score |
|--------------|------------|------------------|
| Template_01 | 246 | 1.92 |
| Template_45 | 230 | 1.78 |
| Template_23 | 224 | 1.72 |

At the end of the output, print the query-template alignment for the best-fit template only.

### 📊 Evaluation Components

| Component | Description | Points |
|------------|-------------|--------|
| **Algorithm Implementation** | Correct and efficient Needleman–Wunsch or Smith–Waterman code | **20** |
| **Handling Input Data** | Proper parsing of query and template FASTA sequences | **10** |
| **Ranking & Output Format** | Correct computation, normalization, and top matches identification | **10** |
| **Code Explanation** | Clear comments, descriptive variables, and logical structure | **5** |
| **Computation Time Measurement** | Accurate reporting of total runtime | **5** |
| **Total** | | **50 points** |
