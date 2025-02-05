# Product Data Auditing Cheatsheet

## Excel Formulas

### 1. **Tier-2 Readiness Scoring Formula**
This formula counts the number of cells in a row that include the Tier-2 identifier (`"2"`):
```excel
=SUMPRODUCT(--(ISNUMBER(SEARCH("2", B3:ZZ3))))
```
This formula calculates the readiness score for each SKU as a percentage of completed Tier-2 data points:
```excel
=(SUMPRODUCT(--(ISNUMBER(SEARCH("2", B$3:ZZ$3)))*(B4:ZZ4<>""))/$A$3)
```
### 2. **Inheritance Restoration Audit Formula**
This formula determines if the data across attributes on the sellable matches or mismatches base:
```excel
=IF(
    B2="",
    "NOT FOUND",
    IFERROR(
        IF(
            AND(
                C2=INDEX(C:C,MATCH(B2,A:A,0)),
                D2=INDEX(D:D,MATCH(B2,A:A,0)),
                E2=INDEX(E:E,MATCH(B2,A:A,0))
            ),
            "DELETE",
            "KEEP"
        ),
        "NOT FOUND"
    )
)
```
