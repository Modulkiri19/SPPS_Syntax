# SPPS_Syntax
Copy Syntax
STRING  Schoo_type (A8). 
COMPUTE Schoo_type=CHAR.SUBSTR(group,1,2). 
VARIABLE LABELS  Schoo_type 'School Type'. 
EXECUTE. 
AUTORECODE VARIABLES=Schoo_type 
  /INTO School_Typ_Recode 
  /PRINT. 
Schoo_type into School_Typ_Recode (School Type) 
Old Value  New Value  Value Label 
s0                 1  s0 
s1                 2  s1 
s2                 3  s2 
s3                 4  s3 
s4                 5  s4 
COMPUTE Total_liter=sum(q5_1,q5_2,q5_3,q5_4,q5_5,q5_8). 
EXECUTE. 
COMPUTE Total_compe=sum(q5_11,q5_12,q5_13,q5_14,q5_15,q5_16,q5_17)*10. 
EXECUTE. 
COMPUTE Total_Liter_score=sum(Total_reading,Total_compe). 
EXECUTE. 
RECODE Total_Liter_score (137.5 thru Highest=1) (Lowest thru 137.49=0) INTO Result_litera. 
VARIABLE LABELS  Result_litera 'Literacy Result'. 
EXECUTE. 
CROSSTABS 
  /TABLES=Result_litera BY Schoo_type 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.
CROSSTABS 
  /TABLES=q1_3 BY School_Typ_Recode 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.
RECODE q6_4 (1=2). 
EXECUTE. 
RECODE q6_5 (1=2). 
EXECUTE.  
RECODE q6_5 (1=2). 
EXECUTE.  
RECODE q6_6 (1=2). 
EXECUTE.  
RECODE q6_7 (1=2). 
EXECUTE.
RECODE q6_8 (1=2). 
EXECUTE.
RECODE q6_9 (1=2). 
EXECUTE.
RECODE q6_10 (1=2). 
EXECUTE.
RECODE q6_11 (1=4). 
EXECUTE.
RECODE q6_12 (1=4). 
EXECUTE.
RECODE q6_13 (1=2). 
EXECUTE.
RECODE q6_14 (1=2). 
EXECUTE.
RECODE q6_15 (1=3). 
EXECUTE.
RECODE q6_16 (1=3). 
EXECUTE.
COMPUTE Total_Numeracy_Score=sum(q6_1,q6_2,q6_3,q6_4,q6_5,q6_6,q6_7,q6_8,q6_9,q6_10,q6_11,q6_12, 
    q6_13,q6_14,q6_15,q6_16,q6_17,q6_18). 
EXECUTE.
RECODE Total_Numeracy_Score (18.5 thru Highest=1) (Lowest thru 18.49=0) INTO Result_Numeracy. 
VARIABLE LABELS  Result_Numeracy 'Numeracy result'. 
EXECUTE.
CROSSTABS 
  /TABLES=School_Typ_Recode BY Result_Numeracy 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.

RECODE q6_4 (1=2). 
EXECUTE. 
RECODE q6_5 (1=2). EXECUTE.  
RECODE q6_5 (1=2). 
EXECUTE.  
RECODE q6_6 (1=2). 
EXECUTE.  
RECODE q6_7 (1=2). 
EXECUTE.  
EXECUTE.  
EXECUTE.  
RECODE q6_8 (1=2). 
EXECUTE.  
EXECUTE.  
RECODE q6_9 (1=2). 
EXECUTE.  
RECODE q6_10 (1=2). 
EXECUTE. 
RECODE q6_11 (1=4). 
EXECUTE. 
RECODE q6_12 (1=4). 
EXECUTE. 
RECODE q6_13 (1=2). 
EXECUTE. 
RECODE q6_14 (1=2). 
EXECUTE. 
RECODE q6_15 (1=3). 
EXECUTE. 
RECODE q6_16 (1=3). 
EXECUTE.  
COMPUTE Total_Numeracy_Score=sum(q6_1,q6_2,q6_3,q6_4,q6_5,q6_6,q6_7,q6_8,q6_9,q6_10,q6_11,q6_12, 
    q6_13,q6_14,q6_15,q6_16,q6_17,q6_18). 
EXECUTE.  
RECODE Total_Numeracy_Score (18.5 thru Highest=1) (Lowest thru 18.49=0) INTO Result_Numeracy. 
VARIABLE LABELS  Result_Numeracy 'Result_Numeracy'. 
EXECUTE.  

EXECUTE.  
RECODE Total_Numeracy_Score (18.5 thru Highest=1) (Lowest thru 18.49=0) INTO Result_Numeracy. 
VARIABLE LABELS  Result_Numeracy 'Numeracy result'. 
EXECUTE.  
CROSSTABS 
  /TABLES=School_Typ_Recode BY Result_Numeracy 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.

COMPUTE Tts_Reading_Edt=sum(q1a3,q1b3,q1c3,q1d3,q1e3,q2a2,q2b2,q2c2,q3a3,q3b3,q3c3,q3d3,q4_3_A, 
    q5_3_A). 
EXECUTE.

COMPUTE Tt_competency_Edt=sum(q5_3_1,q5_3_2,q5_3_3,q5_3_4,q5_3_5,q5_3_6)*10. 
EXECUTE.

RECODE Total_liter_sco (195 thru Highest=1) (Lowest thru 194.99=0) INTO Result_Lit_EdT. 
VARIABLE LABELS  Result_Lit_EdT 'EdTech Literacy Result'. 
EXECUTE.

CROSSTABS 
  /TABLES=School_Typ_Recode BY Result_Lit_EdT 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.

COMPUTE Tt_competency_Edt=sum(q5_3_1,q5_3_2,q5_3_3,q5_3_4,q5_3_5,q5_3_6)*10. 
EXECUTE.

RECODE N_TT (25 thru Highest=1) (Lowest thru 24.99=0) INTO Reslt_Numer_EdT. 
VARIABLE LABELS  Reslt_Numer_EdT 'EdTech numeracy result'. 
EXECUTE.

CROSSTABS 
  /TABLES=School_Typ_Recode BY Reslt_Numer_EdT 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.

# combine Grade 3 and grade 4 for Lateracy
COMPUTE Sum_Lite_G3G4=sum(Result_litera,Result_Lit_EdT). 
EXECUTE.
CROSSTABS 
  /TABLES=q1_8 BY Sum_Lite_G3G4 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL
# Types of school literacty G3G4
CROSSTABS 
  /TABLES=School_Typ_Recode BY Sum_Lite_G3G4 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.
 
# Types of Camparison and Intervention schools
RECODE School_Typ_Recode ('1'=8) ('2'=8) ('3'=9) ('4'=9) ('5'=9) INTO Comp_Inter. 
VARIABLE LABELS  Comp_Inter 'Comparison and Intervension G3G4'. 
EXECUTE.

CROSSTABS 
  /TABLES=Comp_Inter BY Sum_Lite_G3G4 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.

# combine Grade 3 and grade 4 for numercy
COMPUTE Sum_Numer_G3G4=Sum(Result_Numeracy,Reslt_Numer_EdT). 
EXECUTE.

CROSSTABS 
  /TABLES=Comp_Inter BY Sum_Numer_G3G4 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.

CROSSTABS 
  /TABLES=q1_8 BY Sum_Numer_G3G4 
  /FORMAT=AVALUE TABLES 
  /CELLS=COUNT ROW 
  /COUNT ROUND CELL.
