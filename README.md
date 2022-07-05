# Breast Cancer Type Classification Using Machine Learning

Shira Mizrachi 323028845
Efrat Bitton 212367635

breast cancer is a heterogeneous disease defined by molecular types and subtypes. 
Advances in genomic research have enabled the use of precision medicine in clinical management of breast cancer. 
In order to make distinguish the breast cancer subtype, and later on, assign an appropriate treatment, nowadays machine learning is used for a quick diagnosis, especially in critical cases where the timing of the treatment is significant to improve the chances of a successful process.

Breast cancer has four primary molecular subtypes which are defined mostly by hormone receptors (HR) like estrogen receptor and progesterone receptor,
and other types of proteins involved (or not involved) in each cancer type:

Luminal A: HR+/HER2-  ER-positive and/or PR-positive

Luminal B: HR+/HER2+  HER2 positive as well 

Triple-negative: HR-/HER2- Er, Pr, and HER2-negative

HER2-positive HER2+ (ER- and PR-negative)

In this project, using ML tools, we created Breast Cancer Type Classification based on patients' RNA-seq and other information of each patient about disease subtype, hormone expression, a mutation in an oncogene, etc.

# Data - Breast Invasive Carcinoma
The data was taken from the public database TCGA 
(https://www.cbioportal.org/study/summary?id=brca_tcga)
Breast Invasive Carcinoma (TCGA, Firehose Legacy)
TCGA Breast Invasive Carcinoma. Source data from GDAC Firehose. Previously known as TCGA Provisional.
The dataset contains summary data and clinical data from a broad sampling of 1,108 carcinomas from 1,101 patients. 
The data was gathered as part of the Broad Institute of MIT and Harvard Firehose initiative, a cancer analysis pipeline. The clinical data includes mutation count, mutated genes, patient demographics, sample type, etc.


We uploaded the models with the best accuracy to Drive, and tested the prediction using flask.
We used postman in order to send the data in json format to flask, and got a table with the model predictions for er, pr, her2 and subtype
