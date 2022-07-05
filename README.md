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


We noticed that the data is generally consistent with what we expected from previous studies. 
we can see that the proportion of subtypes and expression of HR and proteins in the data is consistent with the finds in the population.
for example, based on a previous review on breast cancer subtypes, luminal-A is the most common subtype and represents 50%-60% of all breast cancer cases and approximately 75% of breast cancers are positive for ER and/or PR.
(https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4127612/) 
In the data, we find the majority to be LumA type with over 50 percent. 
The rest of the observed in the data is also consistent with the expected from literature on the subject.

# PCA
Principal component analysis (PCA) is a statistical procedure that can be used for exploratory data analysis. PCA uses linear combinations of the original data (e.g. gene expression values) to define a new set of unrelated variables (principal components). 
Thus, PCA can be used to reduce the dimensions of a data set, allowing the description of data sets and their variance with a reduced number of variables. 
(https://www.genomatix.de/online_help/help_regionminer/pca.html)

In order to get an impression of the subgroups in the RNA-seq, 
we used PCA to distinguish those subgroups based on HR expression, etc. 
Lowering the dimensions of the RNA-seq with all 50,000+ genes it has to 2D, 
allows us to see with our own eyes whether there is a division of clusters in relation to the subtypes.

for example, the pca of Er:

![image](https://user-images.githubusercontent.com/106597465/177407186-dc638e7d-716a-42ba-ba6e-5e29c4dd69c7.png)

# ExtraTreesClassifier
for every class we explored, we also wanted to extract the 10 most important features by using sklearn ExtraTreesClassifier.
This class implements a meta estimator that fits a number of randomized decision trees (a.k.a. extra-trees) on various sub-samples of the dataset and uses averaging to improve the predictive accuracy and control over-fitting.
Then we presented the top 10 genes associated with the specific class (er, pr, her2, p53, and subtype) using feat_importances.
The top genes associate with Estrogen type of breast cancer

top 10 genes associate with Er

![image](https://user-images.githubusercontent.com/106597465/177407677-8985fbaa-f39c-428a-bb32-4c2384621397.png)

# NOTE
We uploaded the models with the best accuracy to Drive, and tested the prediction using flask.
We used postman in order to send the data in json format to flask, and got a table with the model predictions for er, pr, her2 and subtype
