# MEG data processing
 
Team contributors: Jonathan Gallego, Brainhack School

![Brainstorm image](brainstorm.png)

## This file summarizes the steps taken to preprocess the raw MEG data downloaded from the HCP database

- MEG data preprocessing was conducted in Brainstorm, a Matlab-based open software (https://neuroimage.usc.edu/brainstorm/Introduction)

- This file aims to describe the preprocessing of MEG on a detailed step by step fashion. However if not able to have access to a MATLAB license, you can download the final product of this recipe from the repository (all_subjects_MEG_time_series). Some of these steps are similar to those described in the HCP Brainstorm tutorial (https://neuroimage.usc.edu/brainstorm/Tutorials/HCP-MEG).

- After downloading the MEG data from the HCP database (see HCP_data_download) the first step is to import it to Brainstorm.

- The easiest way to successfully import all the Freesurfer surfaces and have an adequate registration between the MEG coils and the structural MRI is to first load the MEG anatomy HCP folder (selecting the HCP data format) and write down the subject's space and MNI's space coordinates. Then import the complete structural processed data (Freesurfer folder) and set up the coordinates to those of the MEG anatomy folder. This will result in having access to all the surfaces with an accurate registration to the MNI space for all the subjects

- After importing the anatomy, switch to the functional data tab and select review raw data. Then import the corresponding MEG data for each subject. Check the MEG-MRI registration accuracy (if you copied the coordinates as described in the previous step all subjects should be perfectly aligned)

- Draw both the resting MEG and the noise files into the process tab. Select data filtering from the preprocessing menu and apply a notch filter (60 Hz and harmonics), then a high pass filter (0.3 Hz)

- Review the MEG files, mark bad channels to remove them and highlight segments containing excessive movement to exclude them from further analysis

- Select the files on the process tab and from events select detect hearth beats and blinks using the auxiliar ECG and EOG channels respectively

- After quickly checking that the events placed correspond to actual hearth beats and blinks, select the remove simultaneous option from the events tab, to remove the cardiac events close to eye blinks

- Select the remove SSP option from the events tab, and select the components corresponding to cardiac and eye related artifacts in order to regress them out of the data

- Select the files from all subjects and place them in the process tab. From the sources menu select the compute head model option

- Select all the noise fles and place them in the process tab. From the sources menu select the compute noise covariance matrix option

- Select the resting MEG files and place them in the process tab. From the sources menu select the Compute sources (2018) option. From the advanced options select the dSPM method

- Place all the files in the process tab and select the process sources menu. Select the extract scout time series option. Select the desired atlas and time period you want to use for extracting the timeseries. For this project I selected the Destrieux atlas, and extracted the first 60 seconds of signal free from bad segments.

- In order to calculate the functional conectivity for different frequency bands, we can filter the extracted scout timeseries. Then select the scout time series file, and select the option export to matlab from the file menu 

- Having the data as a matlab variable, use the downsample function to resample the timeseries, and arranged the matrices of all subjects to generate the all_subjects_meg_time_series.txt file for each frequency band
