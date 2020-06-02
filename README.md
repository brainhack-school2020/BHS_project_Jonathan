[![](https://img.shields.io/badge/Visit-our%20project%20page-ff69b4)](https://school.brainhackmtl.org/project/template)

# Visualization of functional connectivity from multimodal neuroimaging data - Jonathan
 
Team contributors: Jonathan Gallego, Brainhack School

![BrainHack School](bhs2020.png)

## Summary 

<<<<<<< HEAD
- Hi!, I'm a first year PhD student at McGill. My BHS project aims to use some of the visualization tools we have learned for displaying functional connectivity results from both MEG and fMRI data.
- I'm using data from 12 sample subjects from the Human Connectome Project (https://www.humanconnectome.org).
- I would love to hear from other people projects and see what they have achieved so far!

=======
Hi!, I'm a first year PhD student at McGill. My BHS project aims to use some of the tools we have learned for displaying functional connectivity results from both MEG and fMRI data.
I'm planning  to use data from the Human Connectome Project (https://www.humanconnectome.org).
I would love to hear from other people projects, and if we have similar interests we could team up!
>>>>>>> c938e1d0fdd68e686c87ea366b6f87bcf283d460
twitter: @jogaru1818

### What I wanted to learn

- To manage and analyze data in Python (since I have always worked on Matlab)
- To use some specific tools for neuroimaging analysis (such as nilearn)
- Try different visualization tools for displaying functional connectivity (that could be appliable to different neuroimaging modalities)
- To "Live the experience" of collaborating with others through GitHub


## Project definition

### Background

- Although MEG and fMRI are very different signals, they both reflect some aspects of neuronal activity
- Functional connectivity assess the statistical dependence between the activity (time-series) of different brain regions
- After preprocessing the data individually, we can have both modalities in the same coordinate space, parcellate the brain according to a common atlas and extract the MEG and fMRI time-series of each brain region.
- We then could then compute connectivity measures and visualize the results from both modalities in parallel!

<<<<<<< HEAD
### Tools I employed
=======
- We then could compute some connectivity measures and try to visualize the results from both modalities in parallel!

### Tools 

- Human Connectomme Dataset: As the Open data repository from which I will obtain the data form my BHS project

- GitHub: To create a repository compiling all the resources employed for this project.
>>>>>>> c938e1d0fdd68e686c87ea366b6f87bcf283d460

- Human Connectomme Dataset: As the Open data repository I used for my BHS project
- Git: to keep version control of my files 
- GitHub: To create a repository compiling all the resources employed for this project and make it reproducible.
- Python: As the programming language I used to manipulate manipulate the data.
- Jupyter notebook: As a resource to organize and document the code (with instructions and outputs) I used my project.
- Nilearn tools: As a tool for calculating and displaying functional connectivity from neuroimaging data

### Data specifications

<<<<<<< HEAD
For these project I used data from 12 sample subjects from the Human Connectome Project, including:
=======
### Data 

I will be using data from a small sample of subjects from the Human Connectome Project, including:
>>>>>>> c938e1d0fdd68e686c87ea366b6f87bcf283d460

- Preprocessed high resolution anatomical MR scan
- Preprocessed fMRI resting state data (sesion 1)
- Unprocessed MEG resting state data
- Unprocessed MEG noise recordings
- Anatomical info for MEG registration.

<<<<<<< HEAD
These data can be easily downloaded after creating an account and accessing the Human Connectome Project database (https://db.humanconnectome.org/).
The HCP_data_dowload.md file contains a brief set of instructions of how to get the specific data used for this project
=======

### A brief example of what I mean...

Already dowloaded and started exploring some data

Hands on the MEG data in a familiar environment (Brainstorm)

After registering the sensors to the structural MRI, preprocessing MEG, taking tha data to source space and extracting the time-series of each brain region from the Desillan Killany atlas (68 ROIs)... Here is an example of how the connectivity (correlation) matrix of a single HCP subject look like:

![MEG connectivity matrix](Connect_100307.jpg)


After following the corresponding steps with fMRI, we could also obtain a correlation connectivity matrix, as the one we saw in last week demonstration

![fMRI connectivity matrix (example)](descarga.png)

And now what? Since we have summarized our data into two simple matrices with the same dimesions we could develop some fancy visualization tools to explore the information provided by each modality, or even to make comparisons between modalities!




### What I want to learn

- To manage and analyze data in Python 

- Use some tools for neuroimaging analysis (such as nilearn)

- Try different visualization libraries 

- "Live the experience" of collaborating with others through GitHub

>>>>>>> c938e1d0fdd68e686c87ea366b6f87bcf283d460

### Deliverables

A GitHub repository containing a small set of md files and jupyter notebooks documenting all the requirements, instructions and code needed to reproduce this project. 

### Progress overview and results 

1 The first step was to install all the required software and libraries I needed for my project, and preparing the work environment. Detailed instructions on the requirements you need to fulfil to run the code and replicate these analysis are presented in the requirements.md file
 
2 After installing all the requiered dependencies and dowloading the HCP data I started working on the MEG data. Since the already processed source space MEG data available in the HCP database cannot be manipulated in many ways, I decided to download the raw data and preprocess it myself. Even that I was very interested in learning to perform all these steps using some of the new tools we explored I knew this was not feasible for the time we had for our project, so I performed the preprocessing using a software I am already familiar with (Brainstorm). Once I preprocessed the MEG data and performed a source estimation analysis, I extracted the timeseries of the 148 regions from the Destrieux atlas (2009) for each subject, concatenated them and exported them into a text file. The order of the labels of the scouts was consisted with that used for the fMRI analysis. The detailed step by step description of the MEG processing is contained in the MEG_processing.md file. 

3 For the fMRI data, I opted to use the preprocessed images. I employed functions from nilearn to load the brain parcellations of the Destrieux atlas and the preprocessed fMRI data. As the HCP resting state fMRI consist on 1200 3d brain volumes, loading all the dataset at the same time may cause memory saturation on a regular machine. Therefore, I segmented the nifti files into smaller chunks of data, and created a python code to load each chunk at the time, extract the fMRI timeseries of each scout and concatenated the data for each subject and then from all subjects, and save it into a single matrix. The code used to extract the time series from the fMRI data is contained in the fMRI_timeseries.ipynb jupyter notebook.

4 After having extracted the MEG and fMRI timeseries from the scouts of the atlas I ellaborated a simple code to create a couple of interactive figures to display the functional connectivity matrices and graphs I obtained from the data. These interactive figures allow to easily navigate through the data from all subjects and switch between modalities. The final output of steps 2 and 3 is stored in the all_subjects_time_series_meg.txt and all_subjects_time_series_fmri.txt files, which contain the extracted timeseries of all subjects, for each modality respectively. This last step loads these files, and use a combination of nilearn tools and ipywidgets to create and display an interactive figure, within a jupyter notebook. 
 
## Conclusion and acknowledgement

The BHS team hope you will find this template helpful in documenting your project. Developping this template was a group effort, and benefitted from the feedback and ideas of all BHS students over the years.
