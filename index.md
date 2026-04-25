layout: default
---

# EX09: Data Analysis for Continuous Improvement

## Course Improvement Proposal: Debugging Practice in Assignments


**Authors**: [730748670, 730748019]

This analysis investigates whether students with little to no prior programming experience rely more heavily on office hours, which would support adding explicit debugging instruction to early assignments.

---

## The Proposal

**Idea:** The course should incorporate more debugging practice into assignments.

**Expected Value:** Help students catch their own mistakes earlier, reduce frustration when code fails, and make students more resilient and less reliant on office hours.

**Stakeholders Benefiting:** All students, especially those new to programming.

---

## Data Overview

Two survey datasets were combined for this analysis:
- `survey_izzi.csv` (Alyssa's responses)
- `survey_alyssa.csv` (Izzi's responses)

**Total responses analyzed:** 44 students

**Key columns used:**
- `prior_exp` - Self-reported programming experience before COMP110
- `oh_visits` - Number of office hours visits during the semester

---

## Analysis Methodology

1. Loaded and combined both survey datasets
2. Selected only the `prior_exp` and `oh_visits` columns
3. Filtered out rows with missing `oh_visits` data
4. Converted `oh_visits` to integers for numerical analysis
5. Calculated frequency counts for experience levels
6. Generated visualizations using seaborn

---

## Key Findings

### Experience Level Distribution

| Experience Level | Number of Students |
|-----------------|-------------------|
| None to less than one month | 11 (25.0%) |
| 1 month or so | 4 (9.1%) |
| 2-6 months | 12 (27.3%) |
| 7-12 months | 5 (11.4%) |
| 1-2 years | 4 (9.1%) |
| Over 2 years | 8 (18.2%) |

### Average Office Hours Visits by Experience Level

<img src="/static/imgs/bar_chart.png" alt="Bar chart showing average OH visits by prior experience level" width="700"/>

*Students with no prior experience visited OH slightly more often than experienced students, but the difference was small.*

### Individual Student Distribution

<img src="/static/imgs/strip_plot.png" alt="Strip plot showing individual student OH visits by experience level" width="700"/>

*Most students across ALL experience levels visited OH only 0-2 times.*

---

## Conclusion

### Results: Inconclusive

The analysis did **not** conclusively support the hypothesis that less experienced students rely heavily on office hours.

**Why the results are inconclusive:**
1. `oh_visits` is too broad - doesn't distinguish between debugging help, conceptual questions, or assignment clarification
2. Survey was administered at semester end (students may forget early frustrations)
3. Students who gave up without visiting OH appear as "low-OH" students, masking the real problem

### Recommendations for Future Data Collection

1. **Tag OH tickets** by reason (debugging help, conceptual question, assignment clarification)
2. **Add early-semester survey** (Week 3-4) asking: "How many times this week did you spend 30+ minutes stuck on an error without progress?"
3. **Run an A/B test** - Give debugging instructions to one section, compare OH rates against control section

### Costs and Trade-offs

| Stakeholder | Potential Negative Impact |
|-------------|--------------------------|
| Instructors/TAs | Time to redesign assignments, achieve consensus on debugging priorities |
| Experienced students | May find debugging exercises repetitive or too slow |
| Course schedule | Adding debugging content means removing or shortening other topics |

---

## Visualizations Created

- **Bar chart** - Average OH visits by prior experience level (`seaborn.catplot` with `kind="bar"`)
- **Strip plot** - Individual student distribution showing spread within each group (`seaborn.catplot` with `kind="strip"`)

---

## Repository Structure
*Analysis completed for COMP110 Spring 2026*
