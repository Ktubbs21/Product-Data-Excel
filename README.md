# Product-Data-Excel


=SUMPRODUCT(--(ISNUMBER(SEARCH("2", B3:ZZ3)))) 
=(SUMPRODUCT(--(ISNUMBER(SEARCH("2", B$3:ZZ$3)))*(B4:ZZ4<>""))/$A$3)
