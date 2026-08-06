# Copilot in Excel — Participant Exercise Guide
### Formulas & Pivot Tables for Collections
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `BFL_Collections_Copilot_BasicDemo.xlsx`

---

## Before You Begin

- Open `BFL_Collections_Copilot_BasicDemo.xlsx` from OneDrive
- Click the **Copilot button** (top-right ribbon) to open the Copilot panel
- Keep the Copilot panel open throughout all exercises
- The file has **25 rows of collections data** — one sheet, no formulas yet
- Columns N–Q are intentionally blank — you will fill these using Copilot

---

## Exercise 1 — Add a Formula Column: DPD Bucket

### Your Turn
Click on cell **N3** (first empty cell under "DPD Bucket"), then type this into the Copilot panel:

```
In column N, add a formula that classifies each account into a DPD
bucket based on column D (DPD):
- "Critical" if DPD is more than 90
- "High" if DPD is between 61 and 90
- "Medium" if DPD is between 31 and 60
- "Low" if DPD is 30 or less
Apply the formula to all 25 rows of data.
```

### What Copilot Will Produce
```excel
=IF(D3>90,"Critical",IF(D3>60,"High",IF(D3>30,"Medium","Low")))
```
Copilot will suggest inserting this formula and filling it down to N27.

---

## Exercise 2 — Add a Formula Column: Risk Score

### Your Turn
Click on cell **O3**, then type into the Copilot panel:

```
In column O, create a Risk Score for each account by multiplying
the DPD value (column D) by the Outstanding amount (column E).
Label the column "Risk Score". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=D3*E3
```
Simple multiplication — but Copilot names the column, writes the formula, and fills it down.

---

## Exercise 3 — Add a Formula Column: EMIs Overdue

### Your Turn
Click on cell **Q3**, then type into the Copilot panel:

```
In column Q, calculate the number of EMIs overdue for each account
by dividing the Outstanding amount (column E) by the EMI Amount
(column F). Round the result to the nearest whole number.
Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=ROUND(E3/F3,0)
```

---

## Exercise 4 — Ask Copilot to Explain a Formula

### Your Turn
Click on the formula in **N3** (the DPD Bucket IF formula), then type into Copilot:

```
Explain this formula to me in simple terms. What does each part do?
```

### What Copilot Will Explain
> *"This formula checks the value in D3 (the DPD). If it's greater than 90, it returns "Critical". If not, it checks if it's greater than 60 and returns "High". If not, it checks for greater than 30 and returns "Medium". Otherwise it returns "Low". The IFs are nested — each one only runs if the previous condition wasn't true."*

---

## Exercise 5 — Create a Pivot Table with Copilot

### Your Turn
Click anywhere in the data, then type into the Copilot panel:

```
Create a pivot table that shows the total Outstanding amount for
each Product, broken down by Call Outcome. I want to see which
products have the most escalated or unresolved accounts.
```

### What Copilot Will Produce
A new sheet with a Pivot Table:
- **Rows:** Product (Personal Loan, Home Loan, Gold Loan, Two-Wheeler, Business Loan)
- **Columns:** Call Outcome (PTP Confirmed, Escalated, No Response, etc.)
- **Values:** Sum of Outstanding (₹)

---

## Exercise 6 — Ask for a Second Pivot (Account Count)

### Your Turn
Type into the Copilot panel:

```
Now create another pivot table showing the count of accounts
for each Collector Name, broken down by DPD Bucket (column N).
I want to see each collector's workload by priority tier.
```

### What Copilot Will Produce
- **Rows:** Collector Name (Rajesh Kumar, Sunita Rao, Pooja Sharma, Ravi Patil, Amit Tiwari)
- **Columns:** DPD Bucket (Critical, High, Medium, Low)
- **Values:** Count of Account ID

---

## Copilot Prompts — Quick Reference Card

| Task | Prompt to use in Copilot panel |
|------|-------------------------------|
| Add DPD Bucket column | "In column N, classify each account as Critical / High / Medium / Low based on column D (DPD). Critical = 90+, High = 61–90, Medium = 31–60, Low = 30 or less." |
| Add Risk Score column | "In column O, multiply DPD (column D) by Outstanding (column E) to create a Risk Score. Apply to all rows." |
| Add EMIs Overdue column | "In column Q, divide Outstanding (column E) by EMI Amount (column F) and round to nearest whole number." |
| Explain a formula | "Explain this formula to me in simple terms." |
| Pivot — outstanding by product | "Create a pivot showing total Outstanding by Product and Call Outcome." |
| Pivot — collector workload | "Create a pivot showing count of accounts by Collector Name and DPD Bucket." |
| Highlight overdue accounts | "Highlight all rows where DPD is greater than 90 in red." |
| Sort by risk | "Sort this data by Risk Score from highest to lowest." |

---

*Bajaj Finance Limited | AI Academy — Collections & Recovery | Microsoft Copilot Training Programme*
