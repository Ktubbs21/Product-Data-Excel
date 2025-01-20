# Product-Data-Excel

## 🛠️ Formulas Used

### 1. **Tier 2 Readiness Formula**
This formula counts the number of cells in a row that include the Tier 2 identifier (`"2"`):

```excel
=SUMPRODUCT(--(ISNUMBER(SEARCH("2", B3:ZZ3))))

=SUMPRODUCT(--(ISNUMBER(SEARCH("2", B3:ZZ3)))) 
=(SUMPRODUCT(--(ISNUMBER(SEARCH("2", B$3:ZZ$3)))*(B4:ZZ4<>""))/$A$3)
