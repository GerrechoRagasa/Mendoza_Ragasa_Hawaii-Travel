# Hawaii Travel: Length of Trip

## 1. Group Information
- **Group Name:**
- **Members:**
-   * Mendoza, Jose Roart
-   * Ragasa, Crist Gerrecho C.
- **Assigned Theme: Travel**
- **Topic: Hawaii Travel: Length of Trip**

## 2. Project Overview
- **Dataset Title: Hawaii Travel: Length of Trip**
- **Source (URL or reference): [Kaggle - Hawaii Travel: Length of Trip](https://www.kaggle.com/datasets/csafrit2/hawaii-travel-length-of-trip)**
- **License/Attribution: Open Data Commons / Kaggle Public Domain**
- **Objective:**
1. To examine how visitor length of stay in Hawaii has changed over the years, including long-term trends and the unusual shift during the pandemic period.
2. To compare length of stay across the Hawaiian islands and other locations, in order to see which destinations tend to hold visitors longer and which see shorter visits.

## 3. Flowchart
- Embed your flowchart image here:
  ```markdown
  ![Preprocessing Flowchart](flowchart/Topic_Flowchart_Pair1Surname_Pair2Surname.png)
  ```
- **Decisions in our flowchart:**
- Decisions in our flowchart: The flowchart has four decision diamonds. The first asks whether the file contains footnote or non-data rows. It did: four source and update notes sat at the bottom of the file, so we moved them out of the data table and kept the 117 real rows. The second asks whether any rows are duplicated or completely empty. We found none, so nothing was dropped. The third asks what to do about missing values, which make up 21% of all cells (567 of 2,691). We chose to leave them as blanks instead of imputing, because filling in survey averages would create numbers that were never measured. The fourth asks about the 2020 spike in length of stay. We kept it and marked it in the plots, because it reflects a real pandemic-era change in how people travelled.
- **Changes we made:**
- Our first Colab script already did most of the core cleaning, so the flowchart changed less than it might seem. It separated the footnote rows, trimmed the text, converted the years to numbers, parsed Indicator into Location, sorted logically, kept missing values as blanks, added Years_With_Data, and reshaped to long format. The flowchart follows that same order.

- The main change is the duplicate and empty-row check. The first script only counted fully empty rows and reported them while keeping them in the table. The flowchart turns this into a decision diamond with a “drop them” branch, and the final code adds a duplicate check and removes both kinds of rows. On this dataset the check found none (0 duplicates, 0 empty), so the output is the same, but the process is now explicit and would protect against a messier export.

- We also turned two things that were implicit in the first script into explicit decisions. In the first script, the 21% of empty cells was printed as a quality report, and the 2020 spike was only marked with a dashed line on one plot. The flowchart makes these choices visible as diamonds, with the rejected options shown. We chose to keep missing values as blanks instead of imputing, because imputing would invent survey numbers. We chose to keep the 2020 outlier because it is real pandemic-era data. To support the first choice, we added a data-availability plot (plot 10). The 2020 marker also changed from a dashed line to a shaded band covering 2020 and 2021.

- Two smaller changes sit outside the flowchart’s decision points. The first script produced 2 plots, and the final code produces 10 plus an auto-generated README. The first script also exported an Excel workbook (wide table, long table, a 2019 matrix, and the footnotes on their own sheet). The final code exports CSVs, a zip of the figures and the README instead, so the Excel file was dropped. If you still want it, the export cell is easy to add back.

- The flowchart is a simplified view of the code. It does not draw the safety net that places any unrecognised location or visitor-group label at the end of the sort order instead of losing it.

## 4. Preprocessing Summary
- First, we separated the four footnote rows from the data table. Second, we trimmed stray spaces in the text columns and converted every year column to a numeric type, so that empty cells became proper missing values. Third, we split the Indicator column (“LOS on Oahu”, “LOS in Hilo”) into a clean Location column. Fourth, we checked for duplicate and fully empty rows and found none. Fifth, we sorted the data in a logical order: Statewide first, then the islands, then Hilo and Kona, with visitor groups ordered from general to specific. Sixth, we kept missing values as blanks and added a column counting how many years of data each row has. Seventh, we kept the 2020 outlier and flagged it in the plots. Finally, we reshaped the table into a long format with one row per location, group and year, which gave 2,124 usable observations.

## 5. Visualizations
- Total: **10**
1. Statewide trend (all visitors by air). A line chart of average length of stay from 1999 to 2021, with the pandemic years shaded. Stays rose from 8.9 days in 1999 to a peak of 9.5 in 2011, then drifted down to 8.8 in 2019 before jumping to 10.6 in 2020.
2. First-time vs repeat visitors. Statewide stay length for first-time and repeat visitors, shown against all visitors. Repeat visitors stay about a day longer than first-timers (9.0 vs 8.2 days in 2019). Neither group has a 2020 value.
3. Accommodation type. Statewide stay length for hotel, condo, timeshare and rental-house visitors. Condo-only visitors stay longest, at 10.4 days in 2019 against 7.1 for hotel-only. In 2020 condo stays reached 13.1 days and rental-house stays 12.3.
4. Trip purpose. Honeymoon, wedding, business/meetings (MCI) and visiting-friends-and-relatives visitors compared statewide. Visitors seeing friends and relatives stay longest (10.7 days in 2019, peaking at 14.4 in 2020), while business and meetings visitors stay shortest at around 7 to 8 days.
5. Trend by island. Oahu, Maui, Kauai and Hawaii Island over time. All four started near 6 to 7 days in 1999 and ended near 7 to 8 by 2019. Hawaii Island saw the biggest 2020 jump, from 7.4 to 10.1 days.
6. Location ranking, 2019. Ranked bars of all-visitor stay length across the nine locations before the pandemic. The statewide figure is 8.8 days, followed by Maui at 7.9, while Lanai is lowest at 3.2.
7. Heatmap, group by location (2019). A matrix of stay length where darker cells mean longer stays. The darkest cells are statewide visiting-friends-and-relatives (10.7 days) and statewide condo-only (10.4). The palest cells are Molokai hotel-only (2.4) and Lanai first-time (2.4).
8. 2019 vs 2021 by location. Paired bars showing the pandemic-era shift. Stay length rose in every location, by 0.8 days statewide and by as much as 2.6 on Molokai.
9. Distribution by visitor group. Boxplots pooling all years and locations. Condo-only visitors have the highest median (9.5 days) and the widest spread, while honeymoon and hotel-only visitors have the lowest medians (5.1 and 5.4 days).
10. Data availability map. A statewide grid showing which group-and-year cells contain data. Visitor groups like All visitors, Hotel-only, Condo-only and MCI have all 23 years, but Rental house and B&B have 8 and Family has 10..

## 6. Key Insights
1. Stays shortened slowly, then spiked. Statewide length of stay peaked at 9.5 days in 2011 and slid to 8.8 days by 2019. It then jumped to 10.6 days in 2020, and was still elevated at 9.6 in 2021.
2. Where you go changes how long you stay. In 2019 the longest stays were on Maui (7.9 days), and the shortest were on Lanai (3.2). Neighbouring destinations such as Hilo (3.9) and Molokai (4.5) also had much shorter stays than the main islands.
3. Repeat visitors and condo guests stay longest. Repeat visitors out-stayed first-timers in all 22 years where both have data, and condo-only visitors averaged about three days more than hotel-only visitors in 2019 (10.4 vs 7.1).
4. The pandemic lengthened stays everywhere. Every location recorded longer stays in 2021 than in 2019, with the biggest increases on Molokai, Hilo and Hawaii Island.
5. Some groups cannot support trend conclusions. About 21% of cells are empty, and the Family, B&B and Rental-house groups have only 8 to 10 years of data. Any conclusions about them should be treated as tentative.

## 7. How to Run
- Open the notebook in Google Colab.
- Install dependencies from `requirements.txt`.
