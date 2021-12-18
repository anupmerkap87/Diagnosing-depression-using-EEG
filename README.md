# Can EEG data aid in clinical diagnosis of Major Depressive Disorder (MDD)?
  **Building predictive machine learning model using python [MNE, Antropy and Scipy]**

## Introduction

Mental disorder incidence is increasing rapidly over the past 2 decades with global depression diagnosed patients reaching 322M as of 2015. Major Depressive Disorder (MDD) has become a leading contributor to the global burden of diseases. However, it is diagnosed through a series of interviews carried out by Psychiatrists and Psychologists. The process is not only labor-consuming but also time-consuming. With the rising of tools such as data mining and artificial intelligence, using physiological data to explore new possible physiological indicators of mental disorder and creating new applications for mental disorder diagnosis has become a new research hot topic. Electroencephalography (EEG), as a non-invasive physiological data, provides a direct measure of postsynaptic potentials with millisecond temporal resolution. Since mental disorders, such as depression, are complex brain cognitive disfunction, EEG is naturally the common data that are favored by the researchers.


## Objective

EEG data is typically processed in MATLAB environment and not essentially in Python. The resources available in Python environment are rather limited. Through this project, we plan to bring out resources and libraries available to process EEG data in Python. The main objective for this Capstone project are -

1. Traditional research on the EEG waveforms were done through MATLAB. We will first have to implement all the functions of MATLAB through native Python librarires like MNE, SCIPY, STATSMODEL
2. Build detailed feature engineering for Resting and simulated information (we refer to this as ERP). Here we will try extracting Linear Features (directly extracted from the waveform with minimal manipulation), Non-Linear Features (entropy / energy related variables)
3. Building Classification model that can further differentiate between patients and normal population

## Requirements

The code is set up in python environment (requires Python 3.7 or higher). Other standard packages involved to run the packages includes:
1. Pandas, Numpy, Scipy (for array processing)
2. Matplotlib, Seaborn (for visualization)
3. Sklearn (for model development)

### MNE Library

As described in the introduction dataset, we will need to translate the algorithms/ feature extraction steps implemented in MATLAB to Python. Fortunately, [MNE Library](https://mne.tools/stable/index.html) implements most of the common feature engineering steps. 

To install the MNE library in standard Python Environment: 

!pip install mne

### Antropy Library

For the non linear features we are using a library called Antropy [https://pythonrepo.com/repo/raphaelvallat-antropy].
To install Antropy

!pip install antropy


## Load EEG data into Python Environment

The EEG data was made available to us in 2 formats. The resting stage EEG signals were packed in .mat format and the activity stage EEG signal was available in .raw format.
The experiment set-up that we have is done in two forms -
1. Resting - The files are present in .mat format
2. Simulated activity - The files are present in .raw format

The system that was used to generate these signal is 128 Channel HydroCelGSN.

### Loading of .mat format

mat = scipy.io.loadmat(<file_name>)

### Loading of .raw format

raw = mne.io.read_raw_egi(<file_name>)

### Setting montage

We set the montage for the EEG waveform to 'GSN-HydroCel-128'. More montages can be found in this location [https://mne.tools/stable/generated/mne.channels.make_standard_montage.html#mne.channels.make_standard_montage]
We also dropped the reference electrode 'E129' as it didn't have any significance.

## Signal Filtering and Visualization

We used the hamming window filter for our project. This was particularly done to attenuate any noise. We understand that any signal above 40 Hz would possibly be a noise insitgated by muscle or eye movement. To implement this we used butter band pass filter.

![image](https://user-images.githubusercontent.com/86871884/146227388-d37dead7-949a-431d-97d4-1c3d9522f8d9.png)

### Example Output before filtering

![image](https://user-images.githubusercontent.com/86871884/146227585-7118b45e-61a8-4e31-81ed-aa6fa2282a25.png)

### Example Output after filtering

![image](https://user-images.githubusercontent.com/86871884/146227723-467622f3-f35d-4694-a955-ffd72add14c3.png)

## Feature Extraction

### Linear Features through Numpy

Post reading the EEG waveform through MNE portal, there is a need to be extract the features. 
For linear features we are using numpy to extract the following features:

1. Mean amplitude (peak to peak) of the power signal
2. Median amplitude (peak to peak) of the power signal
3. Maximum amplitude (peak to peak) of the power signal
4. Minimum amplitude (peak to peak) of the power signal
5. Power at alpha
6. Power at beta
7. Power at delta
8. Power at theta

It is important to import numpy to get these features extracted. 

### Non Linear Features through Antropy

While Antropy has capability of extracting many entropy and complexity factors, we have used the following 3 features:

1. SVD Entropy [https://math.stackexchange.com/questions/542035/what-does-svd-entropy-capture]
2. Spectral Entropy [https://www.mathworks.com/help/signal/ref/pentropy.html#:~:text=The%20spectral%20entropy%20(SE)%20of,information%20entropy%2C%20in%20information%20theory.]
3. Permutation Entropy [https://www.aptech.com/blog/permutation-entropy/#:~:text=Permutation%20Entropy%20(PE)%20is%20a,Henry%20and%20Judge%2C%202019).]





