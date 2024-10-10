# MATLAB Live Script Tutorials for MEEG-44403/54403: Machine Learning for Mechanical Engineers
[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=hanhuark/MEEG-54403)
## Instructor: [Han Hu](https://engineering.uark.edu/directory/index/uid/hanhu/name/Han+Hu/)
## Organization: [Department of Mechanical Engineering, University of Arkansas](https://mechanical-engineering.uark.edu/)
### Data source: [Nano Energy and Data-Driven Discovery Laboratory](https://ned3.uark.edu/) <br>
### Funding: [MathWorks Curriculum Development Support program](https://www.mathworks.com/company/aboutus/soc_mission/education.html) (Organized by [Mehdi Vahab](https://www.linkedin.com/in/mehdivahab/))
## Acknowledgments:
The experimental datasets used in the assignments were prepared by [Hari Pandey](https://www.linkedin.com/in/haripandey14/) and the development of the original course content was supported by [Connor Heo](https://www.linkedin.com/in/connor-heo-5b790336/) and [Christy Dunlap](https://www.linkedin.com/in/christy-dunlap/). The course syllabi and content were updated following the comments from the Department of Mechanical Engineering Curriculum Committee (chaired by [Steve Tung](https://mechanical-engineering.uark.edu/Directory/index/uid/chstung/name/Steve-Tung/)) and students enrolled in this course from 2021 - 2023. The tutorials for the assignments were developed by [Najee Stubbs](https://www.linkedin.com/in/najeei/) under the support of a gift from the [MathWorks Curriculum Development Support program](https://www.mathworks.com/company/aboutus/soc_mission/education.html) (organized by [Mehdi Vahab](https://www.linkedin.com/in/mehdivahab/)). 

### Assignment 1 - Regression:
In pool boiling experiments, the boiling heat flux can be estimated as the supplied power divided by the heater surface. However, this estimation will not be very accurate due to heat loss and other non-ideal conditions in experiments, especially for thin-film heaters with relatively low thermal conductivities (e.g., ITO heaters). Conventionally, finite-element simulations are used to evaluate the heat loss to validate or correct the experimental assumptions. Machine learning provides another perspective for tackling this issue. The heat loss and other non-ideal conditions can be captured and accounted for by the hidden layers of neural networks. The target of Problem 1-1 is to develop an MLP model to predict heat flux using temperature. The data set includes the temperature and the heat flux during a transient pool boiling test. 
a.	Set up and train an MLP and a GPR model to predict the heat flux based on the temperature. Report the training curves (training/validation accuracy/loss vs. epoch) and the training time (time/epoch, time till the best model).
b.	Circumvent the effects of overfitting using k-fold cross-validation (e.g., using 100 foldings). 
The dataset for this assignment is provided in the folder. 

### Assignment 2 - Image Classification
Pool boiling is a heat transfer mechanism that dissipates a large amount of heat with minimal temperature increase by taking the advantage of the high latent heat of the working fluids. As such, boiling has been widely implemented in the thermal management of high-power-density systems, e.g., nuclear reactors, power electronics, and jet engines, among others. The critical heat flux (CHF) condition is a practical limit of pool boiling heat transfer. When CHF is triggered, the heater surface temperature ramps up rapidly (~ 150 C/min), leading to detrimental device failures. There is an increasing research interest in predicting CHF based on boiling images. This dataset includes two folders, namely, “pre-CHF” and “post-CHF” that contain pool boiling images before and after CHF is triggered, respectively. The target of this problem is to develop a machine learning model to classify the boiling regime (pre or post CHF) based on boiling images. 
a.	Split the data set into training, validation, and testing. This can be done before training with a separate package “split-folders” or directly in the code during training. 
b.	Set up and train a model to classify the pre-CHF and post-CHF images. Report the training curves (training/validation accuracy/loss vs. epoch) and the training time (time/epoch, time till the best model). Use EarlyStopping for fast convergence. 
c.	Test the model using the reserved test data, report the confusion matrix, accuracy, precision, recall, F1 score, the receiver operating characteristic (ROC), and area under the curve (AUC). 
The dataset for this assignment can be accessed at https://data.mendeley.com/datasets/5kjnphrbsz/1

### Assignment 3 - Dimensionality Reduction and Clustering
Run dimensionality reduction and clustering analysis of the same dataset used in HW-2.
(a)	Run single value decomposition (SVD) or principal component analysis (PCA) of the images and plot the percentage explained variance vs. the number of principal components (PC). 
(b)	Pick a representative image, run PCA and plot the reconstructed images using a different number of PCs (e.g. using PC1, PCs 1-2, PCs, 1-10, PCs 1-20, etc.).
(c)	Calculate the error of the reconstructed images relative to the original image and plot the error as a function of the number of PCs.
(d)	Run a clustering analysis of the boiling images using the PCs (the number of PCs to use is up to your choice) and evaluate the results of clustering. 
This assignment uses the same dataset as Assignment 2: https://data.mendeley.com/datasets/5kjnphrbsz/1

### Assignment 4 - Time Series Regression
The data file vapor_fraction.txt includes the vapor fraction (second column, dimensionless) vs. time (first column, unit: ms) of the boiling image sequences. The data are sampled with a frequency of 3,000 Hz (namely, a time step of 0.33 ms). Develop a recurrent neural network (RNN) model to forecast vapor fraction of future frames based on the past frames, e.g., predicting the vapor fraction profile of t = 33.33 ms – 66 ms using the vapor fraction history of t = 0.33 – 33 ms. Options include regular RNN, bidirectional RNN, gated recurrent unit (GRU), bidirectional GRU, long short-term memory (LSTM), bidirectional LSTM. 
(a)	Develop a baseline model with an input sequence length of 16.33 ms (50 data points) and an output sequence length of 16.33 ms (50 data points). Plot the model-predicted signal vs. the true signal. 
(b)	Vary the input and output sequence lengths to evaluate their effect on the error of the model predictions. 
The dataset for this assignment is provided in the folder. 
