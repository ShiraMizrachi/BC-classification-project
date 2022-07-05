# BC-classification
Shira Mizrachi 323028845
Efrat Bitton 212367635

Breast Cancer Type Classification Using Machine Learning

breast cancer is a heterogeneous disease defined by molecular types and subtypes. 
Advances in genomic research have enabled use of precision medicine in clinical management of breast cancer. 
in order to make a distinguishing of the breast cancer subtype, and later on to assign an appropriate treatment, now days machine learning is used for a quick diagnosis especially in critical cases where the timing of the treatment is significant to improve the chances of successful process.

Breast cancer has four primary molecular subtypes which are defined mostly by hormone receptors (HR) like estrogen receptor and progesterone receptor,
and other types of proteins involved (or not involved) in each cancer type:

Luminal A: HR+/HER2-  ER-positive and/or PR-positive
Luminal B: HR+/HER2+  HER2 positive as well 
Triple-negative: HR-/HER2- Er, Pr and HER2-negative
HER2-positive HER2+ (ER- and PR-negative)

In this project, using ML tools, we created Breast Cancer Type Classification based on patients' rna-seq.

The data was taken from the poblic data base TCGA (https://www.cbioportal.org/study/summary?id=brca_tcga).

now days machine learning is used for a quick diagnosis especially in critical cases where the timing of the treatment is significant to improve the chances of successful process.


We uploaded the models with the best accuracy to Drive, and tested the prediction using flask.
We used postman in order to send the data in json format to flask, and got a table with the model predictions for er, pr, her2 and subtype
