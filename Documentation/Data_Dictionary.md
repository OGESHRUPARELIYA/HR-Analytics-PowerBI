# Data Dictionary

Document the fields in the **anonymized or synthetic** dataset used by the report.

| Field | Data type | Description | Example |
|---|---|---|---|
| Employee Code | Text | An anonymized employee identifier | EMP-001 |
| Name | Text | Use a synthetic name or omit from public data | Alex Example |
| Date | Date | Attendance record date | 2022-05-07 |
| Value | Text | Attendance status code | P |

## Attendance Code Definitions

| Code | Description | Day value / treatment |
|---|---|---:|
| P | Present | 1 attendance day |
| WFH | Work from home | 1 attendance day |
| HWFH | Half-day work from home | 0.5 attendance day |
| WO | Weekly off | Excluded from working-day denominator |
| HO | Holiday | Excluded from working-day denominator |
| PL | Paid leave | 1 leave day |
| HPL | Half-day paid leave | 0.5 leave day |
| SL | Sick leave | 1 leave day |
| HSL | Half-day sick leave | 0.5 leave day |
| BL | Bereavement leave | 1 leave day |
| FFL | Family leave | 1 leave day |
| HFFL | Half-day family leave | 0.5 leave day |
| BRL | Bereavement leave | 1 leave day |
| HBRL | Half-day bereavement leave | 0.5 leave day |
| LWP | Leave without pay | 1 leave day |
| HLWP | Half-day leave without pay | 0.5 leave day |
| ML | Medical leave | 1 leave day |
| HML | Half-day medical leave | 0.5 leave day |

## Calculation Notes

- Attendance equivalent value: `P = 1`, `WFH = 1`, `HWFH = 0.5`; other statuses contribute `0`.
- Attendance rate: attendance equivalent days divided by working days.
- Working-day denominator: recorded rows excluding `WO`, `HO`, and blank status values, subject to the final DAX measure.
- Do not infer absences from missing records unless the source system explicitly defines that rule.
