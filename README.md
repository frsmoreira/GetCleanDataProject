# GetCleanDataProject
## Repo with all the required tasks for the Final Assignment of the Getting and Cleaning Data Course

This final assignment for the Getting and Cleaning Data Course Project consists of different activities. To accomplish that I was required to submit: 1) a tidy data set as described below (‘summarizedFinalTable.csv'); 2) a link to a Github repository with my script for performing the analysis; 3) a code book file (‘CodeBook.md’) that describes the variables, the data, and any transformations or work that was performed to clean up the data; and 4) a README.md file with my script and the explanations of how it  works.

This README.md file explains the different analysis performed over the data collected from the accelerometers from the Samsung Galaxy S smartphone. A full description of the data is available at the zipped files (Original_info_files.zip) or at the site where the data was obtained:
            http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The goal was to transform the original data collected from the accelerometers to a tidier format. To accomplish that a R script (run_analysis.R) was created with the following steps:
-	The original ‘train’, ‘test’, 'attribute names' and ‘activity_labels’ were loaded on the R program (version 3.2.3);
-	The ‘train’ and ‘test’ original data (X_test.txt, y_test.txt, subject_train.txt) were merged together by the ‘cbind’ function to form the 3 total tables (‘totalData’, ‘totalLabelData’, ‘totalSubjectData’);
-	The descriptive activity names (e.g. ‘walking’) listed at the ‘activity_labels.txt’ file were merged to the total label table (‘totalLabelData’) by the merge function;
-	The appropriated descriptive variable names were assigned to the ‘totalData’, ‘mergeLabelActivityData’ and ‘totalSubjectData’ tables;
-	with codeLabel  resulted from the merged the ‘train’ and the ‘test’ data (subject_train.txt);
-	Among all the measured variables at the original data set (‘totalData’) only the ones with mean (mean()) and standard deviation (std()) measurements were selected by the grep function;
-	The ‘totalSubjectData’, ‘mergeLabelActivityData’ and ‘totalData (only selected mean and std attributes) were combined together on a final table (‘finalData’);
-	Finally the ‘finalData’ table were transform in a new table were the variables were reorganized. So first of all, the data were grouped by the ‘SubjectCode’, ‘ActivityLabel’ variables. Then each remaining variables were summarized by computing their mean values.
-	The final tidy table will present the mean of the different measurements (only the mean and std measures) collected by the accelerometers device  during the Samsung Galaxy S smartphone project.
-	The final summarized table was written in to the "summarizedFinalTable.csv" file.

At the Gihub repository (‘https://github.com/frsmoreira/FinalAssignmentGetCleanData.git’) besides the README.md file there are also the following files:
-	The summarized tidy data set ‘summarizedFinalTable.csv';
-	The R script file ‘run_analysis.R’;
-	The ‘CodeBook.md’ file with information from the original and new variables and any transformations or work that were performed to clean up the data;
-	A zipped file ‘Original_info_files.zip’ with the original files ‘features.txt’ (List of all features),’ features_info.txt’ (Information about the variables), ‘README.txt’.
