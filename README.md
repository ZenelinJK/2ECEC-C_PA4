# Data Wrangling and Data Visualization

# LuzViMinda Board Exams
This program aims to do two functions. Both follow the same principle but differ in how they're written. Firstly, `pd.read_excel` was used to read the xlsx file that contained the need information for the function to program. Using function `newdf = df[df(df['grades'] > n)&(df['Track'] == 'Subject')]`, by using these function, the system is able to find and read these given parameters and allows to relay to the final results. The results will then have a final filtering to print out the necessary attributes by using `finaldf = newdf[['Name','Class']]` this will locate the columns that contain these parameters. Which is finally then printed out by the system with the name `Luzo, Divider, Minda`

- Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown Luzon
  
For function `Instru` the results parameters set to view are Name, the courses of GEAS and Electronics, with Electronics requiring a grade of 71 and above to appear. Before that, setting up the attributes and constants to filter out the final results are used. Using this function `LuzInstru = Instru[(Instru['Electronics']>70)&(Instru['Track'] == 'Instrumentation')&(Instru['Hometown'] == 'Luzon')]` this manages to filter out the ones needed for the final results. Which the final result uses `Luzo = LuzInstru[['Name', 'GEAS', 'Electronics']]` to display only these 3 columns.

- Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is constant as Mindanao and gender Female
  
For function `Mindy` the results parameters set to view are Name, Track, Electronics and Average, where the Average must be 55 and higher to appear. Much like the previous function, setting up the primary filter to get the finalized results are needed. Before sorting, the average must be first solved to help sort out the function, using `Mindy['Average'] = Mindy[['Math','Electronics','GEAS','Communication']].mean(axis=1)`. After that, using the function `MindMindy = Mindy[(Mindy['Electronics'])&(Mindy['Hometown'] == 'Mindanao')&(Mindy['Gender'] == 'Female')]` will filter out the needed candidates for the final filter. The final result is then stored into these line `Minda = MindMindy[['Name', 'Track', 'Electronics', 'Average']]` to display these results.

# Grade Visualization
- Create a visualization that shows how the different features contributes to average grade.

This program first reads the xlsx file using `pd.read_excel()`. All the grades are then averaged out using an averaging function `Grades['Average'] = Grades[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)`. This will average the scores of all the students in the list, with all the grades. For this, this will be set to use box plot to show where the general area of the grades are. For each graph used, they follow the same format but with different attributes.

`plt.figure(figsize=(12, 6))`
`sns.boxplot(x='var', y='Average', data=Grades)`
`plt.title('Box Plot of Average Grade by var')`
`plt.show()`
The `figure(figsize=(x,y))` dictates the size of the table, `boxplot(x='var', y='Average', data=Grades)` dictates what type of graph it will visualize, with `x` being the attribute that will be added. Once the attribute has been added, the program will go through the columns to find the one that matches the one in `x`. With `.title()` and `.show` being self explanatory. This is repeated a number of times until all average is has an output.

## Does chosen track in college, gender, or hometown contributes to a higher average score?
By examining the graphs and where the scores are, there is a correlation between colleges, gender, or hometown on how the score is based. However there are different number per category and different mean, and with some reaching higher scores but with lower mean than other.
