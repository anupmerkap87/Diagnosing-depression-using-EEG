Original data used is the MODMA dataset. This can be procured by reaching out to the MODMA team. (http://modma.lzu.edu.cn/data/application/)
One will need to sign and End User License Agreement (EULA) for getting hold of the data. 
The files contained in this repository are:

a) File Name: **Sample_resting_file.mat**

Single patient resting state data extracted using - scipy.io.loadmat(file)
Since the file was too big to be loaded into github, we have taken a sample of the file representing 32 seconds of data. The file has been converted back to .mat format to enable query execution.

b) File Name: **Resting_Summary_limited.csv** 

All features extracted from resting file used for modeling purpose. The features corresponds to 55 patients' data collected from 16 electrodes.
Naming convention followed for the variables are :"<lr/nl_feature_resting_electode number>"
  

c) File Name: **ERP_Summary_limited.csv**
  
All features extracted from resting file used for modeling purpose. The features corresponds to 55 patients' data collected from 16 electrodes.
Naming convention followed for the variables are : "<lr/nl_feature_happy/sad/fear_electode number>"
