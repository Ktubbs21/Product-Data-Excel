# Product Data Auditing Cheatsheet

## Excel Formulas

### 1. **Tier 2 Readiness Formula**
This formula counts the number of cells in a row that include the Tier 2 identifier (`"2"`):
```excel
=SUMPRODUCT(--(ISNUMBER(SEARCH("2", B3:ZZ3))))
```
This formula calculates the readiness score for each SKU as a percentage of completed Tier 2 data points:
```excel
=(SUMPRODUCT(--(ISNUMBER(SEARCH("2", B$3:ZZ$3)))*(B4:ZZ4<>""))/$A$3)
```
