# Diagnosing depression through EEG signals

Mental disorder incidence is increasing rapidly over the past 2 decades with global depression diagnosed patients reaching 322M as of 2015. Major Depressive Disorder (MDD) has become a leading contributor to the global burden of disease. However, it is diagnosed through a series of interviews carried out by Psychiatrists and Psychologists. The process is not only labor-consuming but also time-consuming. With the rising of tools such as data mining and artificial intelligence, using physiological data to explore new possible physiological indicators of mental disorder and creating new applications for mental disorder diagnosis has become a new research hot topic. Electroencephalography (EEG), as a non-invasive physiological data, provides a direct measure of postsynaptic potentials with millisecond temporal resolution. Since mental disorders, such as depression, are complex brain cognitive disfunction, EEG is naturally the common data that are favored by the researchers.

EEG data is typically processed in MATLAB environment and not essentially in Python. The resource available in Python environment are rather limited. Through this project, we plan to bring out resources and libraries available to process EEG data in Python. The main objective for this Capstone project are -

a) Traditional research on the EEG waveforms were done through MATLAB. We will first have to implement all the functions of MATLAB through native Python librarires like MNE, SCIPY, STATSMODEL
b) Build detailed feature engineering for Resting and simulated information (we refer to this as ERP). Here we will try extracting Linear Features (directly extracted from the waveform with minimal manipulation), Non-Linear Features (entropy / energy related variables)
c) Building Classification model that can further differentiate between patients and normal population

# Requirements

As described in the introduction dataset, we will need to translate the algorithms/ feature extraction steps implemented in MATLAB to Python. Fortunately, [MNE Library](https://mne.tools/stable/index.html) implements most of the common feature engineering steps. Along with MNE, we utilized packages in Statsmodel.

Few details on MNE: MNE is considered to Pandas for health care / wearables data. It has interesting functions to extract multi modal features - We invested 2 weeks of our Capstone time on the MNE Tutorials to learn various ways of handling the EEG waveform. While the notebook skims through the best structure of the code that we can bring here, there are series of experimentations that went in the background to attain state that we are in right now
