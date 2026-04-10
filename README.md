# ATS-Optimized Resume Builder & Generator

Welcome! If you are a Software Engineer, Data Scientist, DevOps Engineer, or any tech professional tired of getting automatically rejected by Applicant Tracking Systems (ATS), you are in the right place. 

This repository contains two powerful things:
1. **A Bullet-Proof LaTeX Resume Template:** A meticulously engineered resume format guaranteed to parse cleanly into any ATS (like Workday, Taleo, Greenhouse) and score highly on AI shortlisting platforms (like Eightfold.ai, LinkedIn Recruiter).
2. **An AI Prompt Generator:** A smart instruction file that forces AI assistants (like Claude or ChatGPT) to interview you and generate your resume *for you* using this template. 

---

## 🛑 Why This Template Works

Most modern resumes fail for two reasons: they use invisible tables and graphical formatting that breaks text extractors (giving you an ATS score of 0), or they look visually generic and dense to human recruiters. 

This template fixes both:
- **Zero Parsing Errors:** Built iteratively in LaTeX without using complicated standard-breaking packages. When a system strips this to raw text, the hierarchy (Names, Dates, Jobs, Skills) flows exactly as expected.
- **Micro-Tuned Human Readability:** We use exact line-spacing ratios, explicit vertical padding (`\vspace{4pt}`) to separate jobs, and the clean `helvet` (Helvetica) font. When a human eventually looks at the PDF, their eyes will glide over it rather than being hit with a "wall of text."

---

## 🛠️ Step-by-Step Guide: Generating Your Resume

You do **not** need to know how to code in LaTeX to use this system. Follow these descriptive steps to have the AI build it for you.

### Phase 1: The AI Interview (Using `Resume_Generator_Prompt.md`)

Instead of struggling to write high-impact bullet points yourself, our custom prompt acts as an expert "Resume Engineer" that guides you through the process.

**1. Copy the Prompt**
- Open the file [Resume_Generator_Prompt.md](./Resume_Generator_Prompt.md) located in this repository.
- Highlight **everything** below the dashed line and copy it to your clipboard.

**2. Open Your AI Assistant**
- Open a fresh chat with an advanced Language Model. 
- *(We highly recommend using **Claude 3** or **ChatGPT-4**, as they strictly obey formatting constraints better than smaller models).*

**3. Paste and Start the Interview**
- Paste the copied text into the chat and hit send. 
- The AI will immediately greet you and ask for your Header information first (Name, Email, etc.).
- **Crucial Tip:** Just answer the questions naturally! You don't need to write perfect bullets. Just tell the AI what you did in plain English (e.g., *"I built a caching layer in Redis and it cut down page load times by half"*). The AI is programmed to convert that plain English into a highly optimized, metric-driven bullet point.

**4. Keep Answering**
- The AI will ask for your experiences one by one. Take your time providing the details.
- Once the AI has gathered all your career data, it will automatically combine your answers with our perfect LaTeX template and give you the final `.tex` code in a single code block.

### Phase 2: Compiling Your PDF (Turning Code into a Document)

Once the AI gives you the raw LaTeX code block, you need to compile it into a standard PDF file. If you haven't used LaTeX before, the easiest method is **Option A**.

#### Option A: The "No-Install" Browser Method (Overleaf)
1. Navigate to **[Overleaf.com](https://www.overleaf.com/)** and create a free account.
2. Click the green button: **New Project** $\rightarrow$ **Blank Project**. Name it something like "My Resume 2024".
3. Overleaf will load a default editor screen. On the left side, you code. On the right side, it shows the PDF.
4. Delete *all* the default code that Overleaf put in the `main.tex` file.
5. Paste the final LaTeX code that Claude/ChatGPT generated for you into `main.tex`.
6. Click the green **Recompile** button at the top. Your compiled PDF will appear on the right side.
7. **Review and Make Necessary Changes:**
   - Look at the right-side preview. Did it spill onto a second page? If yes, edit the text on the left side (like trimming an older job) and hit **Recompile**.
   - Make sure your links (GitHub/LinkedIn) are correct.
   - Adjust spacing if necessary by modifying the `\vspace{4pt}` tags to `\vspace{2pt}` if you desperately need extra room.
8. **Download:** Once it looks perfect and fits on exactly one page, click the "Download PDF" icon located on the top right of the PDF preview window.

#### Option B: The "Local Hacker" Method (CLI tool)
If you already have a LaTeX distribution (like MacTeX or TeX Live) installed on your machine:
1. Create a raw text file on your computer named `Resume_Final.tex`.
2. Paste the AI-generated LaTeX string into that file and save it.
3. Open your terminal, navigate to the folder where the file lives, and run:
   ```bash
   pdflatex Resume_Final.tex
   ```
4. This command will execute and generate `Resume_Final.pdf` in the exact same folder.

---

## 📈 Best Practices For Maintaining Your 95+ Score

If you decide to manually edit the `.tex` file later to add a new job or skill, keep these stringent rules in mind:

1. **Keep it to One Page:** Recruiters and AI systems favor brevity. If your resume spills onto a second page, review your oldest jobs (5+ years ago) and reduce them from 3 bullet points down to just 1 summarization bullet.
2. **Metrics Are Mandatory:** AI shortlisting tools rank you based on "measured impact". If you write "Managed a team," an AI ignores it. If you write "Managed a cross-functional team of 4 engineers," the AI scores you highly. Always find a number (TPS throughput, percentage reductions, dollar values).
3. **Do Not Touch the Preamble:** The top ~20 lines of the LaTeX file (before `\begin{document}`) are the "Preamble." Do not mess with these package calls, list separations, or geometry lines. They have been mathematically adjusted to maximize readable whitespace.
4. **Bold Your Keywords:** Notice how technologies (e.g., \textbf{Java}, \textbf{AWS}) are bolded inside your job experience bullet points? This acts as a visual anchor for human eyes scanning down the page in 6 seconds. Keep this pattern going for new bullets you add!
