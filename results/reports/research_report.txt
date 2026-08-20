
================================================================================
COMPUTATIONAL IDENTIFICATION AND RANKING OF CONSERVED HIV-1 p24 EPITOPE CANDIDATES
================================================================================

Date: 2026-08-20 14:03

--------------------------------------------------------------------------------
SUMMARY
--------------------------------------------------------------------------------

- Total sequences analyzed: 185 HIV-1 p24 sequences from NCBI
- Alignment length: 235 positions (MAFFT)
- Conservation method: Shannon entropy
- Total unique peptides: 10,112 (MHC-I: 3,557, MHC-II: 6,555)
- Final candidates: 21 prioritized epitope candidates

--------------------------------------------------------------------------------
TOP 5 CANDIDATES
--------------------------------------------------------------------------------

1. GPKEPFRDY (MHC-I)
   - Score: 0.590
   - Support: 182/185 sequences
   - Conservation: 0.976

2. PKEPFRDYV (MHC-I)
   - Score: 0.590
   - Support: 182/185 sequences
   - Conservation: 0.974

3. QGPKEPFRD (MHC-I)
   - Score: 0.589
   - Support: 182/185 sequences
   - Conservation: 0.973

4. KEPFRDYVD (MHC-I)
   - Score: 0.589
   - Support: 182/185 sequences
   - Conservation: 0.973

5. NKIVRMYSP (MHC-I)
   - Score: 0.589
   - Support: 181/185 sequences
   - Conservation: 0.976

--------------------------------------------------------------------------------
B-CELL EPITOPE CANDIDATE
--------------------------------------------------------------------------------

Rank 21: KVVEEKAFSPEVIPM (MHC-II)
- Score: 0.480
- Support: 41/185 sequences
- Conservation: 0.974
- B-cell evidence: Literature-supported

--------------------------------------------------------------------------------
FULL CANDIDATE LIST
--------------------------------------------------------------------------------

 1. GPKEPFRDY    MHC-I   Score: 0.5904  Support: 182/185  Cons: 0.9760  B-cell: False
 2. PKEPFRDYV    MHC-I   Score: 0.5898  Support: 182/185  Cons: 0.9740  B-cell: False
 3. QGPKEPFRD    MHC-I   Score: 0.5895  Support: 182/185  Cons: 0.9728  B-cell: False
 4. KEPFRDYVD    MHC-I   Score: 0.5895  Support: 182/185  Cons: 0.9728  B-cell: False
 5. NKIVRMYSP    MHC-I   Score: 0.5888  Support: 181/185  Cons: 0.9760  B-cell: False
 6. TACQGVGGP    MHC-I   Score: 0.5881  Support: 181/185  Cons: 0.9736  B-cell: False
 7. EPFRDYVDR    MHC-I   Score: 0.5879  Support: 181/185  Cons: 0.9728  B-cell: False
 8. MTACQGVGG    MHC-I   Score: 0.5877  Support: 181/185  Cons: 0.9724  B-cell: False
 9. GLNKIVRMY    MHC-I   Score: 0.5869  Support: 183/185  Cons: 0.9588  B-cell: False
10. LNKIVRMYS    MHC-I   Score: 0.5869  Support: 181/185  Cons: 0.9695  B-cell: False
11. PFRDYVDRF    MHC-I   Score: 0.5866  Support: 180/185  Cons: 0.9740  B-cell: False
12. LGLNKIVRM    MHC-I   Score: 0.5820  Support: 180/185  Cons: 0.9588  B-cell: False
13. HQAAMQMLK    MHC-I   Score: 0.5819  Support: 179/185  Cons: 0.9637  B-cell: False
14. MMTACQGVG    MHC-I   Score: 0.5818  Support: 181/185  Cons: 0.9526  B-cell: False
15. GHQAAMQML    MHC-I   Score: 0.5802  Support: 178/185  Cons: 0.9637  B-cell: False
16. VGGHQAAMQ    MHC-I   Score: 0.5756  Support: 181/185  Cons: 0.9320  B-cell: False
17. EEMMTACQG    MHC-I   Score: 0.5736  Support: 181/185  Cons: 0.9253  B-cell: False
18. EMMTACQGV    MHC-I   Score: 0.5716  Support: 180/185  Cons: 0.9241  B-cell: False
19. GGHQAAMQM    MHC-I   Score: 0.5707  Support: 178/185  Cons: 0.9320  B-cell: False
20. GSDIAGTTS    MHC-I   Score: 0.5680  Support: 172/185  Cons: 0.9557  B-cell: False
21. KVVEEKAFSPEVIPM MHC-II  Score: 0.4798  Support:  41/185  Cons: 0.9744  B-cell: True

--------------------------------------------------------------------------------
LIMITATIONS
--------------------------------------------------------------------------------

1. HLA-restricted prediction was not performed - MHC-I/MHC-II binding was
   predicted using peptide extraction and conservation, not with NetMHCpan.

2. B-cell epitopes are literature-supported - Not experimentally validated.

3. In-silico prioritization only - Results require experimental validation.

4. Single protein target - Only p24 was analyzed.

--------------------------------------------------------------------------------
RECOMMENDED NEXT STEPS
--------------------------------------------------------------------------------

1. Experimental validation of top 5 candidates
2. HLA binding assays (e.g., ELISPOT, MHC multimer)
3. B-cell epitope validation (ELISA, peptide microarray)
4. Expand analysis to other HIV-1 proteins (Env, Nef, etc.)

--------------------------------------------------------------------------------
END OF REPORT
================================================================================
