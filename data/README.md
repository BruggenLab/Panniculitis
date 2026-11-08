# Data (not shared)

This folder is not part of the public repository (patient data, restricted access; see the Data Availability statement of the paper). The analysis files expect:

- `spe_all.rds`, `images.rds`, `masks.rds` - created by `01_IMC_read_data.Rmd` from the steinbock output
- `spe_all_annoted_Final.rds`, `TestInteractions.rds` - created by `03_IMC_Clustering.Rmd`
- `patient_groups.R` - clinical annotation of the IMC patients (private; used by `04_IMC_Figures.Rmd`)
- `PHOTO-2022-06-10-04-10-59.csv`, `PHOTO-2022-06-10-04-10-59.jpg.csv` - nSolver-normalised nCounter counts
- `DE results - TypeEN.csv`, `DE results - TypeEI.csv` - nSolver differential expression results (EN or EI vs HC)
- `ClinicalMetadata.xlsx` - clinical annotation of the nCounter samples
- `AB_quantification/` - ImageJ measurement tables (`*_Results.csv`) of the immunofluorescence images
