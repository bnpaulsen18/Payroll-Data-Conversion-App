# Sample Data Files

This folder contains synthetic sample data for testing and demonstration purposes.

**Company:** Acme Manufacturing
**Employees:** 20 fake employees with realistic payroll data

---

## Source Files (Input)

These files simulate what you might receive from a legacy Great Plains (GP) payroll system.

### sample_legacy_payroll_export.csv
A flat CSV file with combined employee and address data in GP format.
- **Columns:** EMPLOYID, FRSTNAME, LASTNAME, SOCSCNUM, ADDRESS1, CITY, STATE, etc.
- **Use Case:** Simple single-file upload test

### sample_employee_master.xlsx
Multi-sheet Excel workbook mimicking a full GP database export.
- **Sheet UPR00100:** Employee Master (core employee data)
- **Sheet UPR00102:** Employee Address
- **Sheet UPR00300:** Federal Tax Setup
- **Sheet UPR00700:** State Tax Setup
- **Sheet DD00200:** Direct Deposit / Deductions
- **Use Case:** Full multi-sheet upload test with all data types

### sample_deduction_codes.csv
Reference table of deduction codes.
- **Columns:** Code, Description, Type, Pre-Tax, Employer Match
- **Use Case:** Lookup table for deduction mappings

### sample_earnings_codes.xlsx
Reference table of earnings/pay codes.
- **Columns:** Code, Description, Type, Taxable, Overtime Eligible
- **Use Case:** Lookup table for pay type mappings

---

## Output Files (Result)

These files show what the converter produces.

### sample_output_template.xlsx
Business Central (BC) / Payroll Now format output.
- **Sheet Payroll Employee:** Employee demographics and contact info
- **Sheet Payroll Employee Salary:** Pay rates and salary configuration
- **Sheet Payroll Employee Deduction:** Benefit and deduction assignments
- **Sheet Employee State WH Setup:** State tax withholding configuration
- **Sheet US Federal WH Setup:** Federal tax withholding configuration
- **Use Case:** Example of successful conversion output

---

## Data Notes

- **SSNs:** All fake (555-XX-XXXX pattern, not valid)
- **Addresses:** Fictional Michigan addresses
- **Phone Numbers:** Fake 555-XXXX exchange
- **Names:** Common American names, no real people
- **Dates:** Random hire dates 2015-2024, birth dates 1960-1998

---

## Regenerating Sample Data

To regenerate these files with new random data:

```bash
python samples/generate_samples.py
```

Requires: `pip install openpyxl` for Excel file generation.
