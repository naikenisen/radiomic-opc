# 🧠 MICCAI Computational Precision Medicine (CPM) Grand Challenge  
## Predicting Local Tumor Control in Oropharyngeal Cancer Using Radiomics and Clinical Data

---

## 📖 Description

Cancers arising from the head and neck have become increasingly more studied in the past few years, especially cancers of the oropharynx which are now epidemic domestically, with over 20,000 annual cases projected in the U.S. Growing evidence has established differential clinical, pathological, molecular, and epidemiological attributes between human papilloma virus-associated (HPV+) and HPV-negative (HPV-) oropharyngeal cancer (OPC) disease entities.

Recent data suggest that **radiomics**, or extraction of image texture analysis to generate mineable quantitative data from medical images, can reflect phenotypes for various cancers. Several groups have shown that developed radiomics signatures, in head and neck cancers among other tumor sites, can be correlated with survival outcomes. Radiomics features from metabolic imaging modalities, like **18F-fluorodeoxyglucose Positron Emission Tomography (18F-FDG PET)** have been postulated as surrogates for underlying tumor biology, and hence prognosis.

This competition is organized as a **Medical Image Computing and Computer Assisted Intervention (MICCAI) Computational Precision Medicine (CPM)** grand challenge. Contestants are tasked to predict, using primary tumor 18F-FDG PET-derived radiomics features ± matched clinical data, whether a tumor arising from the oropharynx will be controlled by definitive radiation treatment (RT).

The **University of Texas MD Anderson Cancer Center (MDACC)** head and neck radiation oncology team curated and harmonized a multi-institutional dataset of **248 oropharyngeal cancer (OPC) patients**, using the in-house *LAMBDA-RAD* data management platform.  
Scans were collected from six institutes:

- **US**: MD Anderson Cancer Center (MDACC)  
- **Canada**: Four Québec institutions — Hôpital Général Juif de Montréal (HGJ), Centre Hospitalier Universitaire de Sherbrooke (CHUS), Centre Hospitalier de l’Université de Montréal (CHUM), and Hôpital Maisonneuve-Rosemont (HMR)  
- **Europe**: MAASTRO Clinic, The Netherlands

---

## ⚙️ Challenge Workflow

This dataset encompasses anonymized **18F-FDG-PET DICOM-RT files**, and expert-segmented contours of primary tumors propagated from computed tomography (CT) to PET scans (*DICOM-RTSTRUCT*).  
It also includes relevant clinical data, known etiological/biological correlates, and **tumor control outcomes** as ground truth.

The main goal is to assess the ability of participant-developed radiomics workflows to predict binary outcomes (local tumor recurrence) using a defined **training cohort** that includes all input and outcome data.

Participants should anticipate real-life clinical challenges, including:
- Tumor segmentation and image co-registration
- Inter-scanner variability

---

## 📅 Timeline and Submissions

All participants in the MICCAI challenge are required to provide:
- A **1-page abstract** or **up to 4-page computational algorithm report**
- Submission deadline: **August 30, 2018**
- Upload link: [Dropbox submission portal](https://www.dropbox.com/request/rsIk3dGq5a9G8V3FBv2u)

Accepted abstracts will be published in the **Springer Lecture Notes in Computer Science (LNCS)** collection.  
Updates can be made until **November 1**, after the conference.  
Top 3 team members will be included as co-authors in the final report manuscript.

---

## 👥 Organizer & Contact

**Hesham Elhalawani, MD, MSc**  
*Email:* [hmelhalawani@mdanderson.org](mailto:hmelhalawani@mdanderson.org)  
*Phone:* +1-713-792-9582  

### Acknowledgements

We wish to thank the following collaborators:

- **MD Anderson Cancer Center (TX, US):**  
  Clifton D. Fuller, MD, PhD (Team Lead), Abdallah Mohamed, MD, MSc, Hesham Elhalawani, MD, MSc, Sarah Westergaard, BS, Xiaodong Zhang, PhD, Lee Li Liao, BS, Carlos E. Cardenas, MSc, Sweet Ng, MD, MPH, Ben W. Edwards, Juan D. Ventura, Baher Elgohari, MD, MSc, Pei Yang, MD, MPH, Mohamed A.M. Meheissen, MD, MSc, Timothy A. Lin, BS, Aaron Grossberg, MD, PhD  
- **McGill University (Québec, Canada):** Martin Vallières, PhD  
- **MAASTRO Clinic (The Netherlands):** Andre Dekker, PhD, Leonard Wee, PhD  
- **Massachusetts General Hospital (US):** Jayashree Kalpathy-Cramer, PhD  
- **NCI/MICCAI:** Keyvan Farahani, PhD  

---

## 🧮 Evaluation

Participants will be ranked according to the **Matthews Correlation Coefficient (MCC)** calculated on the private subset of the test set.

### Dataset Split
- **Training set:** Half of the 18F-FDG PET files (DICOM-RT format)
- **Test set:** Remaining half, with a **public subset** for leaderboard ranking

### Scoring Process
1. Public leaderboard: performance on public test subset  
2. Private leaderboard: final ranking based on hold-out subset  

Each team may submit **two final models** for evaluation.

---

## 🩻 DICOM Resources

**DICOM (Digital Imaging and Communications in Medicine)** is the standard format for managing medical images and related metadata.  
Several open-source texture analysis tools can be used to extract radiomics features:

- [**IBEX (Imaging Biomarker Explorer)**](https://sourceforge.net/projects/ibex-mda/?source=directory) — MATLAB / C++
- [**Pyradiomics**](http://www.radiomics.io/pyradiomics.html) — Python package for radiomics feature extraction  
- [**MazDa**](http://www.eletel.p.lodz.pl/programy/mazda/index.php?action=mazda) — C++ / Delphi© texture parameter calculator  
- [**CGITA**](http://code.google.com/p/cgita) — MATLAB-based texture analysis toolbox  

If you know of additional open-access software, please contact: [hmelhalawani@mdanderson.org](mailto:hmelhalawani@mdanderson.org)

---

## 📄 Submission Format

Submission files must be **.csv** sheets with two columns:

| **Subject_ID** | **local_control** |
|----------------|-------------------|
| 001 | 1 |
| 002 | 0 |
| ... | ... |

A sample submission file is provided for reference.

---

## 📊 Data Variables

| **Variable name** | **Definition** |
|--------------------|----------------|
| **Subject_ID** | Randomly assigned number for each patient after anonymization of the original identifier. Enables cross-referencing between imaging and clinical data. |
| **Age_at_diagnosis** | Patient’s age (in years) at the time of diagnosis. |
| **Sex** | Patient’s gender. |
| **p16_expression** | Human Papilloma Virus (HPV) status, assessed through p16 protein expression using immunohistochemistry (IHC). |
| **T_category** | Describes the original (primary) tumor in terms of size and extent, based on the American Joint Committee on Cancer (AJCC) and Union for International Cancer Control (UICC) cancer staging system. [More information](https://cancerstaging.org/references-tools/Pages/What-is-Cancer-Staging.aspx). |
| **N_category** | Indicates whether or not the cancer has spread to nearby lymph nodes, according to the AJCC and UICC cancer staging system. [More information](https://cancerstaging.org/references-tools/Pages/What-is-Cancer-Staging.aspx). |
| **AJCC_7th_edition** | AJCC cancer stage according to the 7th edition. [More information](https://cancerstaging.org/references-tools/Pages/What-is-Cancer-Staging.aspx). |
| **AJCC_8th_edition** | Updated AJCC cancer stage (8th edition). [Reference](https://onlinelibrary.wiley.com/doi/full/10.3322/caac.21389). |
| **Vital_status** | Vital status of the patient at the date of last contact. |
| **Local_control** | Presence or absence of pathological or clinical (examination/radiographic) evidence of local recurrence of the patient’s malignant tumor within the same cancer site of origin, as of the date of last contact. |

---

## 🧾 Notes

- All data are anonymized and ethically compliant.  
- AJCC staging follows international cancer classification standards.  
- The dataset may be linked to imaging data for multi-modal analyses.

Dataset Description
File descriptions

Training.csv - clinical data for the training dataset

Test.csv - clinical data for the test dataset

Sample_valid_submission.csv - a sample submission file in the correct format

ReadMe.csv - includes supplemental information about the headings of the columns in the datasets

Training.zip - A compressed folder that contains anonymized DICOM files of the training dataset. The subfolders are named according to each patient's ID after de-identification. Each individual patient's subfolder includes pre-treatment PET DICOM-RT files, and DICOM-RTSTRUCT file which includes manually segmented primary tumors (originally contoured on CT scan then propagated to the provided PET scan.

Test.zip - A compressed folder that contains anonymized DICOM files of the test dataset. The subfolders are named according to each patient's ID after de-identification. Each individual patient's subfolder includes pre-treatment PET DICOM-RT files, and DICOM-RTSTRUCT file which includes manually segmented primary tumors (originally contoured on CT scan then propagated to the provided PET scan.
Data fields

Subject_ID - Numbers given randomly to the patient after anonymizing the patient's original identifier number

Age_at_diagnosis - Patient's age in years at the time of diagnosis

Sex - Patient's gender [Female/Male]

p16 expression - Human Papilloma Virus (HPV) status, as assessed by p16 protein expression via immunohistochemistry (IHC), with the results described as: Positive or Negative

T_category - The T category describes the original (primary) tumor, as regard its size and extent, per the American Joint Committee on Caner (AJCC) and Union for International Cancer Control (UICC) cancer staging sysytem. It could be T1, T2, T3, T4. https://cancerstaging.org/references-tools/Pages/What-is-Cancer-Staging.aspx

N_category - The N category describes whether or not the cancer has reached nearby lymph nodes, per the AJCC and UICC cancer staging sysytem. It can be N0, N1, N2 or N3. https://cancerstaging.org/references-tools/Pages/What-is-Cancer-Staging.aspx

AJCC_7th_edition - AJCC cancer stage. https://cancerstaging.org/references-tools/Pages/What-is-Cancer-Staging.aspx

AJCC_8th_edition - The most updated AJCC cancer stage. https://onlinelibrary.wiley.com/doi/full/10.3322/caac.21389

Vital_status - Vital status of the patient as of the date of last contact. [Alive or Dead]

Local_control - Records the presence or absence of pathologic or clinical (examination/radiographic) evidence of the patient's malignant tumor locally, i.e. within the same cancer site of origin; as of the date of last contact. It is coded as: Yes (i.e. control) or No (i.e. recurrence)
DICOM file structure set descriptors

GTVp - Gross Primary Tumor Volume