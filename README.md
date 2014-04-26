Assignment-Tidy-Data
====================
I used the read.table function to load the different files needed, which are kept under a folder /data in the working directory. I assume that the files have been downloaded and extracted already. I set as.is=TRUE to have integers and numbers instead of factors.
I used cbind to join subject_train, Y_train and X_train (7352 rows), then did the same for subject_test, Y_test and X_test (2947 rows) then used rbind to merge the train and test data sets. The resulting data.frame has dimension 10299 by 563
After loading features.txt, I applied grep successively to "mean()" and "std()" (with fixed=TRUE) to retrieve only the actual mean and standard deviation (33 variables for each), leaving aside the variables with meanFreq.
I then used a subset of the original data.frame, keeping only the subject of the activity number (integer from 1 to 6), the subject number (integer from 1 to 30) and the 33*2 means and standard deviations. I then renamed  the columns of the data.frame thanks to colnames.
I used the merge function to create a character variable of the activity name (WALKING, WALKING_UPSTAIRS ,WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING). I then convert subject and activity into factors, so that I can use the split function on the data set, broken down over those 2 factors. 
I then use sapply to retrieve the mean per column (removing the 3 non numeric columns which are related to  activity and subject). I end up with matrix of 66 rows (the measures) and 180 columns (30 subjects * 6 activities).
<<<<<<< HEAD
Finally, after loading the reshape package, I used the melt function to get a tiny data set with activity as the first column (character), subject as the second column (integer), measure as the thirs column (character) and the mean of the measure for a given activity and subject (numeric).
=======
Finally, after loading the reshape package, I used the melt function to get a tiny data set with activity as the first column (character), subject as the second column (integer), measure as the thirs column (character) and the mean of the measure for a given activity and subject (numeric). 
>>>>>>> ce4f605fb083087e5da7fe785813de77919d2c77
