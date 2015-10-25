<h2>Introduction</h2>
The script run_analysis.Rperforms the 5 steps described in the course project's definition.

<li>First, all the similar data is merged using the <code>rbind()</code> function. By similar, we address those files having the same number of columns and referring to the same entities.</li>
<li>Then, only those columns with the mean and standard deviation measures are taken from the whole dataset. After extracting these columns, they are given the correct names, taken from <code>features.txt.</code></li>
<li>As activity data is addressed with values 1:6, we take the activity names and IDs from <code>activity_labels.txt</code> and they are substituted in the dataset.</li>
<li>On the whole dataset, those columns with vague column names are corrected.</li>
<li>Finally, we generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called <code>averages_data.txt</code>, and uploaded to this repository.</li>
<h2> Variables</h2>
<li><code>x_train</code>, <code>y_train</code>, <code>x_test</code>, <code>y_test</code>, <code>subject_train</code> and <code>subject_test</code> contain the data from the downloaded files.</li>
<li><code>x_data</code>, <code>y_data</code> and <code>subject_data</code> merge the previous datasets to further analysis.</li>
<li>features contains the correct names for the <code>x_data</code> dataset, which are applied to the column names stored in mean_and_std_features, a numeric vector used to extract the desired data.</li>
<li>A similar approach is taken with activity names through the <code>activities</code> variable.</li>
<li>all_data merges <code>x_data</code>, <code>y_data</code> and <code>subject_data</code> in a big dataset.</li>
<li>Finally, <code>averages_data</code> contains the relevant averages which will be later stored in a .txt file. <code>ddply()</code> from the plyr package is used to apply <code>colMeans()</code> and ease the development.</li>
