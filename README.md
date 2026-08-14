# Swim Program Scheduling & Capacity Analysis

## Overview
This project analyzes class scheduling, enrollment, and capacity data for a municipal swim program operating across three pools. Using Power BI, I built a relational data model connecting class schedules, instructor assignments, and pool information to identify where scheduling and staffing were misaligned with actual demand — and to model a response to an upcoming operational change.

## Business Question
Which class times and pool locations are over- or under-utilized relative to capacity, and how should the program adjust its schedule to protect enrollment as one of its three pools closes after this summer?

## Approach
- Built a relational data model in Power BI connecting five tables: Classes, Pools, Instructors, Class_Instructors (a bridge table linking instructors to the specific classes they teach), and Swimmer_Progression
- Calculated a **Fill Rate %** measure (Enrolled ÷ Capacity) using DAX to standardize comparison across pools and shifts of different sizes
- Built a heatmap matrix visualizing enrollment, capacity, and fill rate broken out by pool and shift (Morning/Night)
- All swimmer and instructor data was anonymized using ID codes rather than names

## Key Finding
Pool utilization varies significantly by location and shift:

| Pool / Shift | Enrolled | Capacity | Fill Rate |
|---|---|---|---|
| Pool 1 – Morning | 968 | 980 | **99%** |
| Pool 2 – Morning | 394 | 652 | **60%** |
| Pool 2 – Night | 528 | 644 | **82%** |
| Pool 3 – Morning | 236 | 336 | **70%** |

Pool 1 mornings are running at essentially full capacity, while Pool 2 mornings sit at just 60% — over a third of available seats are empty. Pool 2 also currently runs the program's only night classes. With Pool 2 scheduled to close after this summer, the program stands to lose both its night-class capacity and a meaningful share of its morning capacity, representing a real loss in potential enrollment revenue if that demand isn't redirected elsewhere.

## Recommendation
Because Pool 1 mornings are already running near full capacity, there is no room to absorb Pool 2's closure by simply shifting more morning classes there. Instead:

1. **Pool 1 should begin offering night classes for the first time**, using its confirmed facility capability to pick up the night-class demand currently served by Pool 2, rather than losing that revenue entirely.
2. **Pool 3, which has meaningful room in the mornings (70% capacity) and will remain open**, can absorb some of the displaced morning demand.

Together, these two changes would let the program retain most of Pool 2's enrollment capacity through its two remaining pools, rather than losing it when Pool 2 closes.

## Tools Used
Power BI Desktop (data modeling, DAX measures, visualization) · Excel (data collection and structuring)

## Files in This
- `Swim_Program_PowerBI_Template_FINAL.xlsx` — anonymized source data (Classes, Pools, Instructors, Class_Instructors, Swimmer_Progression)
- `Swim_Program_PowerBI.pbix` — Power BI project file
- `PowerBI_Swim_Screenshot.png` — final dashboard visual

---
*Note: All data has been anonymized. Instructor and swimmer names were replaced with ID codes prior to analysis, and this repository contains no personally identifiable information.*
