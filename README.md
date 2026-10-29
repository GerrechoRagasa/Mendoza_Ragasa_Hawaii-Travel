# 📘 MEXE Electives 2: Midterm Project on Data Preprocessing

## 🔹 Project Overview
Each pair will take the assigned **theme** , find a real-world dataset, **draw a flowchart of your preprocessing plan**, write the program, and produce **10 meaningful visualizations** using Python in **Google Colab**.

- Work must be uploaded in this **central GitHub repository**.
- Each group will have their own folder named:
  ```
  <Pair1Surname>_<Pair2Surname>_<Topic>
  ```
- Inside the folder, include your **flowchart**, **Google Colab notebook**, **cleaned dataset**, and a **README.md** (use the template provided).

---

## 📅 Deadlines
- **Topic (to Instructor):** Friday, **October 16, 2026, until 5:00 PM**
  - Submit pair name, dataset (title + source), your flowchart, planned 10 visualizations, and preprocessing steps (at least 3).

- **Final Submission (GitHub):** Monday, **October 26, 2026, until 11:59 PM**.
- **Presentation (GitHub):** Tuesday, **October 27, 2026**.

---

## 📂 Repository Structure
```
MEXE_E2_Midterm/
│
├── Pair1Surname_Pair2Surname_Topic/
│   ├── flowchart/
│   │   └── Topic_Flowchart_Pair1Surname_Pair2Surname.png
│   ├── notebooks/
│   │   └── Topic_Midterm_Pair1Surname_Pair2Surname.ipynb
│   ├── data
│   │   └── DATA_SOURCE.txt   # if dataset too large
│   ├── README.md             # pair project summary
│   └── requirements.txt
│
├── Pair1Surname_Pair2Surname_Topic/
│   └── ...

```
---

## 📝 Student Instructions

### Step 1. Topic Submission
By the deadline, send to the instructor:
- Pair names or Individual name if no partner
- Topic
- Dataset (title + source link)
- Planned 10 visualizations (list + short purpose)
- Planned preprocessing tasks (at least 3)

### Step 2. Draw Your Flowchart First

**Do not open Colab yet.** Draw the flowchart of your preprocessing program before you write any code.

**Use a drawing tool.** draw.io (free, at app.diagrams.net), Lucidchart, Canva, or Microsoft Word shapes. **Hand drawn flowcharts are not accepted.**

**Your flowchart must cover all of these:**

1. Start
2. Load the dataset
3. Inspect the data (shape, data types, summary)
4. Missing values, with what you do on each branch
5. Duplicate rows, with what you do on each branch
6. Fixing data types, if your dataset needs it
7. Outliers, with what you do on each branch
8. Encoding your categorical columns
9. Scaling your numerical columns
10. Saving the cleaned dataset
11. The loop that produces your 10 visualizations
12. End

**Rules:**

- Write the real column names from your own dataset, not "column A". The flowchart is about your data.
- Keep it to one page. If it will not fit, make a second flowchart for the visualization loop.
- Save it as **PNG or PDF** inside your `flowchart/` folder.

### Step 3. Project Work

- **Put your flowchart image at the very top of your Colab notebook**, in the first markdown cell, before any code.
- Preprocess the dataset step by step, following your own flowchart. Please see the attached Ch9 notebook for reference (handle missing values, duplicates, data types, outliers, and so on).
- **Your code must match your flowchart.** I will read them side by side. If you change your mind while coding, go back and update the flowchart.
- Add a short markdown note above each code block saying which box of the flowchart it carries out.
- Generate at least **10 visualizations** that provide real insights.
- Add short captions for each visualization.

### Step 4. Upload to GitHub
- Create your pair folder: `<Pair1Surname>_<Pair2Surname>_<Topic>`
- Include:
  - **Flowchart** in `flowchart/`
  - **Notebook** in `notebooks/`
  - **Dataset** in `data/`
  - **README.md** using the template below
  - **requirements.txt** listing libraries (pandas, numpy, seaborn, matplotlib, and so on)

### Step 5. Presentation
- Present directly from your GitHub folder.
- Duration: **3 to 6 minutes**.
- Flow: Dataset, then Flowchart, then Preprocessing, then 3 key visuals, then Insights.
- Start with your flowchart on screen. Walk us through it in 30 seconds before you show any code.

---

## 📊 Visualization Requirements
At least **10 plots**, including:
- 2 distribution plots (histograms, KDE)
- 2 multivariate plots (scatter, pairplot)
- 1 correlation heatmap
- 1 missingness plot
- 1 categorical comparison (bar / countplot)
- 1 box/violin plot (spread / outliers)
- 1 temporal plot (if applicable)
- 1 advanced (PCA / clustering / grouped heatmap)

---

## ✅ Grading (100 pts)
- Flowchart: 10 pts
  - Drawn with a drawing tool, correct symbols, 3 pts
  - All 12 required steps present, 4 pts
  - Code matches the flowchart, 3 pts
- Preprocessing: 20 pts
- Visualizations: 25 pts
- Code and reproducibility: 15 pts
- Documentation: 10 pts
- Presentation and deadlines: 20 pts

**No flowchart means no grade for the preprocessing section.** The program is graded against the plan, so without the plan there is nothing to grade it against.

---

# 📑 Group README Template

Each group must include a `README.md` file inside their folder. Use this format:

## 1. Group Information
- **Group Name:**
- **Members:**
- **Assigned Theme:**
- **Topic:**

## 2. Project Overview
- **Dataset Title:**
- **Source (URL or reference):**
- **License/Attribution:**
- **Objective:** (1 or 2 sentences about what you want to show with this dataset)

## 3. Flowchart
- Embed your flowchart image here:
  ```markdown
  ![Preprocessing Flowchart](flowchart/Topic_Flowchart_Pair1Surname_Pair2Surname.png)
  ```
- **Decisions in our flowchart:** list each decision diamond and what you chose on each branch.
- **Changes we made:** if the code ended up different from your first flowchart, say what changed and why.

## 4. Preprocessing Summary
- List preprocessing steps you applied, in the same order as your flowchart.

## 5. Visualizations
- Total: **10**
- Short description + insight for each plot.

## 6. Key Insights
- 3 to 5 main findings from your data.

## 7. How to Run
- Open the notebook in Google Colab.
- Install dependencies from `requirements.txt`.
