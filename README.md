# HR Analytics Dashboard - Power BI Graduation Project

## 1. Project Overview & Proposal
**Problem Statement:**
The HR department currently lacks a centralized system to monitor workforce dynamics. High employee turnover (attrition) and the disconnect between employee satisfaction and performance ratings often go unnoticed until it's too late. Manual reporting leads to data silos and delayed decision-making.

**Project Goal:**
To design and develop an interactive Power BI dashboard that provides actionable insights into:
* **Employee Attrition:** Identifying drivers like overtime, salary, and tenure.
* **Performance vs. Satisfaction:** Analyzing the correlation between manager ratings and employee happiness.
* **Workforce Demographics:** Visualizing diversity across departments and job roles.
* **Compensation Equity:** Ensuring fair pay across genders and ethnicities.

---

## 2. Project Timeline & Milestones
| Phase | Milestone | Key Deliverables |
| :--- | :--- | :--- |
| **Week 1** | Planning & Proposal | Definition of KPIs and Project Scope |
| **Week 2** | Data Engineering | Power Query cleaning & Star Schema modeling |
| **Week 3** | DAX Development | Development of Attrition and Performance measures |
| **Week 4** | Visualization & Final Report | Interactive Dashboard & Graduation Documentation |

---

## 3. Data Sources & Requirements
The project utilizes five core datasets (CSV format):
* **Employee.csv:** Primary workforce data (1,470 records).
* **PerformanceRating.csv:** Historical performance reviews (6,709 records).
* **EducationLevel.csv:** Metadata for educational background.
* **RatingLevel.csv:** Legend for performance scores.
* **SatisfiedLevel.csv:** Legend for satisfaction scores.

---

## 4. Key Business Questions & KPIs
The dashboard answers the following:
1.  What is the current **Attrition Rate** and which job roles are most affected?
2.  Is there a correlation between **Distance from Home** and Job Satisfaction?
3.  How do **Manager Ratings** compare to **Self-Ratings** across departments?
4.  What is the average **Promotion Lag** (years since last promotion)?

**Primary Metrics (DAX):**
* `Total Employees = COUNTROWS(Employee)`
* `Attrition Rate = DIVIDE(CALCULATE(COUNT(Employee[Attrition]), Employee[Attrition]="Yes"), [Total Employees])`
* `Avg Satisfaction = AVERAGE(PerformanceRating[JobSatisfaction])`
* `Training Participation = DIVIDE(SUM(PerformanceRating[TrainingOpportunitiesTaken]), SUM(PerformanceRating[TrainingOpportunitiesWithinYear]))`

---

## 5. Domain Context (Literature Review)
Modern HR Analytics shifts the focus from administrative record-keeping to strategic workforce optimization. By analyzing lead indicators like "Satisfaction Level" and "Years with Current Manager," organizations can predict turnover before it happens. This project follows industry standards for People Analytics to drive data-informed retention strategies.

---

## How to Run the Project
1.  Clone this repository.
2.  Open the `.pbix` file using Power BI Desktop.
3.  Ensure the CSV data sources are linked to the local path if prompted.
4.  Interact with the slicers to filter by Department, Gender, or State.
