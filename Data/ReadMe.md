Original data used is the MODMA dataset. This can be procured by reaching out to the MODMA team. (http://modma.lzu.edu.cn/data/application/)
One will need to sign and End User License Agreement (EULA) for getting hold of the data. 
The files contained in this repository are:

a) File Name:

Single patient active state data extracted using - mne.io.read_raw_egi(path,verbose=True)
The array of data was then converted into a csv file and saved for reference. Detailed extraction and analysis process can be seen in the Colab Notebook

b) File Name: **Sample_resting_file.mat**

Single patient resting state data extracted using - scipy.io.loadmat(file)
Since the file was too big to be loaded into github, we have taken a sample of the file representing 32 seconds of data. The file has been converted back to .mat format to enable query execution.

c) File Name: **Resting_Summary_limited.csv** 

All features extracted from resting file used for modeling purpose. The features corresponds to 55 patients' data collected from 16 electrodes.
Naming convention followed for the variables are :"<lr/nl_feature_resting_electode number>"
  

d) File Name: **ERP_Summary_limited.csv**
  
All features extracted from resting file used for modeling purpose. The features corresponds to 55 patients' data collected from 16 electrodes.
Naming convention followed for the variables are : "<lr/nl_feature_happy/sad/fear_electode number>"
