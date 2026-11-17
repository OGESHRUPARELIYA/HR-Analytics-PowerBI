# HR Analytics Dashboard | Power BI

An interactive HR attendance dashboard built with Microsoft Power BI to monitor workforce attendance, work-from-home activity, leave usage, and employee-level attendance patterns.


## Dashboard Pages

### 1. HR Analytics Dashboard
- Workforce attendance KPIs
- Monthly attendance trends
- Attendance distribution
- Leave type analysis
- Monthly workforce overview

### 2. Employee 360° Analysis
- Employee-level attendance KPIs
- Monthly status breakdown
- Daily attendance register
- Attendance performance

## Key Performance Indicators (KPIs)

| KPI | What it measures | Calculation / treatment |
|---|---|---|
| **Total Employees** | Employees represented in the selected data context | Distinct count of employee identifiers |
| **Attendance Rate** | Share of working days credited as attendance | Attendance Equivalent Days ÷ Working Days |
| **Present Days** | Full days marked as present | Count of records with status `P` |
| **WFH Days** | Work-from-home attendance, including half days | `WFH = 1` day; `HWFH = 0.5` day |
| **Total Leave Days** | Full-day and half-day leave taken | Full-day leave codes = `1`; half-day leave codes = `0.5` |
| **Working Days** | Recorded days treated as working days | Non-blank records, excluding `WO` and `HO` |

### Attendance Rate Details

Attendance credits used in the numerator:

- `P` (Present) = **1**
- `WFH` (Work from home) = **1**
- `HWFH` (Half-day work from home) = **0.5**
- Leave statuses = **0** attendance credit

`WO` (Weekly off) and `HO` (Holiday) are excluded from the Working Days denominator.

**Formula:**

`Attendance Rate = (Present + WFH + Half-day WFH equivalent days) / Working Days × 100`

The Working Days KPI is based on recorded rows, excluding weekly offs, holidays, and blank status values. It should not be interpreted as scheduled workdays if attendance records are missing.

## Tools
- Microsoft Power BI
- Power Query
- DAX
- Microsoft Excel


## Repository Structure
```text
HR-Analytics-PowerBI/
├── README.md
├── Dashboard/HR Analytics Dashboard.pbix
├── Screenshots/
│   ├── Page 1.png
│   └── Page 2.png
├── Dataset/Attendance-Sheet-2022.xlsx
├── Documentation/
│   ├── DAX_Measures.txt
│   └── Data_Dictionary.md
└── .gitignore
```

## Dashboard Preview

### HR Analytics Dashboard
![HR Analytics Dashboard](Screenshots/dashboard_overview.png)

### Employee 360° Analysis
![Employee 360 Analysis](Screenshots/employee_360_analysis.png)

## How to Use
1. Clone or download this repository.
2. Open `Dashboard/HR_Analytics_Dashboard.pbix` in Power BI Desktop.
3. If prompted, update the data source to the sample workbook in `Dataset/`.
4. Refresh the report.

## Documentation
- [DAX Measures](Documentation/DAX_Measures.txt)
- [Data Dictionary](Documentation/Data_Dictionary.md)
