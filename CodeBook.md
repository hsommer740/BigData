# Introduction to script: 

The script labelled `run_analysis.R`performs the 5 steps described in the course project's definition.

1) Data with the same numbrr of columns and entities are merged using the `rbind()` function.
2) Then, column mean and standard deviation measures are calculated where possible from the whole dataset. After extracting these columns, they are given the correct names, taken from `features.txt`.
3) Activity data is given values 1:6, while the activity names and IDs are extracted from `activity_labels.txt` and then substituted in the dataset.
4) Columns with vague column names are then corrected.
5) Finally, we generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called `averages_data.txt`. Thde filke has been uploaded to the repository.

# Here is an explanation of the variables included in the analysis:

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain data from the downloaded files.
* `x_data`, `y_data` and `subject_data` merge the previous datasets for further analysis.
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_and_std_features`. The latter is a numeric vector used to extract the desired data.
* A similar approach is taken with activity names through the `activities` variable.
* `all_data` merges `x_data`, `y_data` and `subject_data` into one big dataset.
* Finally, `averages_data` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()` and ease the development.
