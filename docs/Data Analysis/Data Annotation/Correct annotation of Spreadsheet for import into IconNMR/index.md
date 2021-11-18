# Correct annotation of Spreadsheet for import into IconNMR

Authors: Marie Phelan & Rudi Grosman 
Revision Date: 1 November 2017

A spreadsheet should be provided with each batch of samples the information of this spreadsheet will be used to annotate the sample spectra therefore it is important to be as clear as possible with information.

Please fill columns out in the following order

A .csv file can be created using any text or spreadsheet editor.

Essential inputs are:

- **Study Name and Date [COL_A]:** File name in which the results will be saved. Please do NOT use spaces or special characters - only use text, number & underscore. For example Plasma_antibiotics_150114 is a plasma antibiotic study submitted on 15th October 2014.

- **Solvent [COL_B]:** Which solvent is used in your sample? These depend on biomaterial and extraction procedure; for biofluids (blood, urine etc) state “H2O+D2O”, aqueous cell or tissue extracts “D2O”, lipophilic extracts either “MeOD” or “CDCl3” – if in doubt ask

- **Experiment [COL_C]:** These are experiments set at the spectrometer – this can be left blank or set to the default is PROF_noesy 

- **Position in NMR rack [COL_D]:** These are the positions of the samples as prepared for NMR – if not yet prepared for NMR leave this blank.

- **Unique identifier [COL_E]:** researchers own short-hand identity code for the sample.

- **Storage Tube ID [COL_F]:** The annotation on the storage tube also should be recorded -for clarity we recommend numbering consecutively from 1 to n (n = total number of samples). If samples in 96-well block provide row and column position. A1, B1, C1, D1, E1, F1, G1, H1 then A2, B2, C2, D2, E2, F2, G2, H2 etc.

- **Cohort [COL_G] and replicate [COL_H]:** identity for the cohort and biological/technical replicate number. If time course is provided this may be added as an additional column.

- **Study details [COL_I]:** provide details of the study (investigator, institute, area of study)

  

Example of Spreadsheet format of a .csv file:

| COL_A                     | COL_B   | COL_C      | COL_D | COL_E | COL_F | COL_G     | COL_H | COL_I                        |
| ------------------------- | ------- | ---------- | ----- | ----- | ----- | --------- | ----- | ---------------------------- |
| Plasma_antibiotics_150114 | H2O+D2O | PROF_noesy | A1    | PT121 | 121   | Control   | 1     | Clinical study Li-Hep Plasma |
| Plasma_antibiotics_150114 | H2O+D2O | PROF_noesy | B1    | PT124 | 124   | Control   | 2     | Clinical study Li-Hep Plasma |
| Plasma_antibiotics_150114 | H2O+D2O | PROF_noesy | C1    | PT127 | 127   | Control   | 3     | Clinical study Li-Hep Plasma |
| Plasma_antibiotics_150114 | H2O+D2O | PROF_noesy | D1    | PT131 | 131   | Infection | 1     | Clinical study Li-Hep Plasma |
| Plasma_antibiotics_150114 | H2O+D2O | PROF_noesy | E1    | PT144 | 144   | Infection | 2     | Clinical study Li-Hep Plasma |

PROF_noesy A1 PT121 121 Control 1 Clinical study Li-Hep Plasma Plasma_antibiotics_150114 H2O+D2O PROF_noesy B1 PT124 124 Control 2 Clinical study Li-Hep Plasma Plasma_antibiotics_150114 H2O+D2O PROF_noesy C1 PT127 127 Control 3 Clinical study Li-Hep Plasma Plasma_antibiotics_150114 H2O+D2O PROF_noesy D1 PT131 131 Infection 1 Clinical study Li-Hep Plasma Plasma_antibiotics_150114 H2O+D2O PROF_noesy E1 PT144 144 Infection 2 Clinical study Li-Hep Plasma

- All the information entered is case sensitive so make sure it is exactly the same.
- When saving csv file ensure field delimiter is set to comma `,`.
- **DO NOT** use commas anywhere in the file Once done make sure you save the spreadsheet as a .csv file and check it with a text editor (such as notepad) to make sure it fits the format required. 