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



After importing the data, we wanted to explore it from different angles. in order to do so, we looked at the data by creating simple pie charts.


First we checked the subtype of the patients. 

![image](https://user-images.githubusercontent.com/106597465/177398772-f3f95228-4dd2-49fb-a2f4-da976b8186aa.png)

Then we looked at the mutaion in p53 gene.

![image](https://user-images.githubusercontent.com/106597465/177399787-8b658eb8-cd3d-4732-b557-fd384151375e.png)

And then we look into the state of expression or non-expression of ER, PR, and HER2.

ER


![ER](https://user-images.githubusercontent.com/106597465/177400507-8fc238b3-58fe-46a6-b335-c144acbbb56d.png)

PR


![PR](https://user-images.githubusercontent.com/106597465/177400511-20796f91-3e88-4933-b6cf-6b991ddfcadc.png)


HER2

![HER2](https://user-images.githubusercontent.com/106597465/177400517-8d4bebf4-302d-4118-a396-e117d1d24a37.png)




# NOTE
We uploaded the models with the best accuracy to Drive, and tested the prediction using flask.
We used postman in order to send the data in json format to flask, and got a table with the model predictions for er, pr, her2 and subtype
