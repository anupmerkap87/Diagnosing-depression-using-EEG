The files contained in this repository are:

a) File Name:

Single patient active state data extracted using - mne.io.read_raw_egi(path,verbose=True)
The array of data was then converted into a csv file and saved for reference. Detailed extraction and analysis process can be seen in the Colab Notebook

b) File Name: 

Single patient resting state data extracted using - scipy.io.loadmat(file)
The array of data was then converted into a csv file and saved for reference. Detailed extraction and analysis process can be seen in the Colab Notebook

c) File Name: **Resting_Summary_limited.csv** 

All features extracted from resting file used for modeling purpose. The features corresponds to 55 patients' data collected from 16 electrodes.
Naming convention followed for the variables are - <lr/nl>_<feature>_<resting>_<electode number>

d) File Name: **ERP_Summary_limited.csv**
  
All features extracted from resting file used for modeling purpose. The features corresponds to 55 patients' data collected from 16 electrodes.
Naming convention followed for the variables are - <lr/nl>_<feature>_<happy/sad/fear>_<electode number>
