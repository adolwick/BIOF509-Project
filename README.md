# Predicting User Presence in VR with Behavioral Data
_by Alex Dolwick_

### Conceptual Background

Virtual reality (VR) tools are useful for behavioral research because they provide a happy medium between the two most common settings for behavioral studies: the lab and the field. Lab studies are highly controlled, but lab environments are artificial and often do not approximate the real world well enough for participants to behave naturally. Field studies measure natural behavior, but field environments are uncontrolled by researchers and often contain noise and potential confounds. VR studies have the best of both worlds, with VR environments being highly controlled and evoking natural behavior in participants. This latter point, however, depends on participants' _presence_ in VR environments.

Presence is the psychological concept describing a sense of being in a place. Applied to VR, presence refers to the extent to which users feel that they exist within the virtual world. Prior research has demonstrated that generally, participants in VR studies self-report high levels of presence. This allows for researchers to obtain natural reactions to stimuli in behavioral studies conducted in VR environments.

The present tool is designed to predict self-reported presence of users in a VR environment by analyzing nonverbal behavioral data automatically collected by the VR system. These data are measured on 6 degrees of freedom (6DOF) that represent both positional data (x, y, and z) and rotational data (yaw, pitch, and roll). While designed for this specific purpose, the tool is flexible enough to work with any data in which there is one observation per row and one variable per column (i.e., tidy data) and in which all features are numeric.  

### Sample Data

The data I am using to exhibit this tool were collected in a VR Buffet environment for a study in Dr. Susan Persky's lab at the National Human Genome Research Institute. Each participant (_N_ = 216) was instructed to make a meal by selecting food items in the buffet to put onto their plate. They spent as much time as they wanted in the VR environment. 6DOF data were collected every half-second. The raw data includes data out to the last half-second for the participant who spent the longest in the VR Buffet, resulting in data from 0.5 seconds to 462.5 seconds. For participants who spent a shorter amount of time than 462.5 seconds in the VR Buffet, values for every half-second after their exit are marked as missing.

### Use

This repository contains six raw data files in .csv format, one for each degree of freedom. Additionally, it contains five annotated Jupyter Notebook files, marked numerically by their order in the pipeline, as follows:


1_KNN_imputation -- Imputes values for missing data.

2a_PCA -- Performs dimensionality reduction via principal component analysis.

2b_UMAP -- Performs dimensionality reduction via UMAP.

3a_RFR -- Predicts VR user presence using the random forest regressor.

3b_SVR -- Predicts VR user presence using the support vector regressor.


Each Jupyter Notebook runs its algorithm via the following format: requisite packages are imported, a class is initialized that contains all necessary methods to conduct and evaluate the algorithm, and an object of that class is created to run the algorithm on the sample data. To use this tool on the sample data, run through the Jupyter Notebook files in order.

