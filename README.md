# pandas-challenge
Module 4 Challenge - UWA Data Analytics Bootcamp

PyCitySchools folder contains PyCitySchools.ipynb, PyCitySchools_starter.ipynb, Analysis.txt and Resources file.
PyCitySchools.ipynb is the main code, PyCitySchools_starter.ipynb contains starting code and model answers provided, Analysis.txt contains the text below.
The Resources folder contains 2 CSV files which holds all analysed data. 

SUMMARY:

The data contained within the schools_complete.csv and students_complete.csv is first summarised into a "LGAsummary_df" data frame.
From this data frame we note that the CSVs contain entries from 15 different schools and 39,170 students. Notably, the overall pass rate (i.e. the number of students who passed in both maths and reading) was 72.81% (2dp).

The data is then grouped by school, in order to summarise (at each school) the type of school, number of students, budgets, scores and pass rates.

We use this grouping to determine the top 5 performing and bottom 5 performing schools (by overall pass rate), noting Griffin High School to be the top performer and Hernandez High School to be the worst performer.

We then conditionally determine the math and reading score averages for each year group (years 9 - 12).

Using bins, we are then able to cut the maths & reading scores/pass rates into different spending ranges per student (school budget / Number of Students).
The bins used were: <$585, $585-630, $630-645, $645-680.
We determine the average performance metrics of each bin of schools.

Similarly, we then cut by school size (number of students).
The bins used were: Small (<1000), Medium (1000-2000), Large (2000-5000)

Lastly, we cut by school type (i.e. Government or Independent schools)

ANALYSIS:

The data suggests that Independent Schools consistently perform better than Government Schools.
This is supported when considering the Scores by School Type (TypeBinnedAvgs_df), as we can see the averages presented are higher in each category for the Independent Schools bin.
This conjecture is also supported when considering the Top Performing Schools (By % Overall Passing) (TopPerformingSch_df) and Bottom Performing Schools (By % Overall Passing) (WorstPerformingSch_df).
3/5 of the top schools were Independent, whilst 4/5 of the bottom schools were Government.

The data also suggests that smaller schools perform better than larger schools.
The Scores by School Size (SizeBinnedAvgs_df) demonstrates that small (<1000 students) schools have the highest average scores and pass rates, with large schools (2000-5000) having the lowest averages.
The Medium (1000-2000) schools sit in the middle in terms of it's averages, with it's results being closer to that of small schools.


REFERENCES:

pandas.DataFrame.apply was required when handling already grouped data frames for conditional filtering of columns
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.apply.html

pandas.DataFrame.replace was required remove string items from a column in order to properly cut/bin data (as number is needed to compare to bin numbers)
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.replace.html

pandas.DataFrame.astype was required to convert column data to numbers (from string) as again, a number is needed to compare to bin numbers
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.astype.html