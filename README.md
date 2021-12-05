# <u> Fundamentals of Data Analysis </u>
## Author: Conor McCaffrey

![jupyter.png](Images/jupyter.png)
<i>Reference 1 </i>

This repository contians Jupyter notebooks and relevant files demonstrating the use of `pandas` , `numpy` , `matplotlib` and other packages in the analysis of CAO points from 2021,2020,2019 and the exploration of the `matplotlib.pyplot` Python package.

![matpy.png](Images/matpy.png)
<i>Reference 2</i>

The `pyplot.ipynb` notebook serves as an overview of the `matplotlib.pyplot` Python package. Here, I have described the background and advantages of using `matplotlib`, the dual interfaces of `matplotlib` and then gone into extensive detail on three plots available in the package. 

This notebook is not only of use to those who want to gain familiarity with `matplotlib`, but it also serves as a resource for how to edit parameters of plots available in the package. This notebook is a resource that can be visited numerous times to solve a range of issues regarding the plotting of datasets in `python` and `jupyter`.

You can view the static version of the  `pyplot.ipynb`  notebook by clicking the following button:

[![nbviewer](https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.org/github/conor-mccaffrey/fundamentals_of_Data_Analysis/blob/main/pyplot.ipynb)


Alternatively, you can view the notebook in dynamic form by clicking the following button:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/conor-mccaffrey/fundamentals_of_Data_Analysis/main?filepath=pyplot.ipynb)

***
The notebook `cao-points-analysis.ipynb` contains a detailed analysis of CAO points in 2019, 2020 and 2021. Some interesting observations were deducted from our analysis. This is acheived through the incorporation of `pandas` dataframe, histograms, scatterplots and pie-charts. `Matplotlib` , `seaborn` and `plotly` were heavily incorporated for this notebook. `Plotly` was brought into this notebook as I believe the plots to be more accessible than through `matplotlib`. A challenge here however, is that `plotly` will not render on GitHub (so in this case I saved the figures and laoded them onto the notebook) but they render perfectly using `nbviewer` and `binder`.

This notebook would be suitable for people looking to see differences in points between certain CAO courses over the period 2019-2021 and also for identifying trends in courses (i.e Top 5 courses). I think this would be a beneficial tool for everyone as I don't think it currently exists (not that I have seen anyway).

You can view the static version of the  `cao-points-analysis.ipynb`  notebook by clicking the following button:

[![nbviewer](https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.org/github/conor-mccaffrey/fundamentals_of_Data_Analysis/blob/main/cao-points-analysis.ipynb)


Alternatively, you can view the notebook in dynamic form by clicking the following button:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/conor-mccaffrey/fundamentals_of_Data_Analysis/main?filepath=cao-points-analysis.ipynb)


### Installation

1. Download Anaconda if space permits. 
2. Alternatively, download the latest version of Python (3.10.0).
3. Consult `requirements.txt` for packages used in the notebook. 

### Run

Here is how to run the `cao-points-analysis.ipynb` notebook:
1. Open cmdr terminal.
2. Go to notebook location.
3. Run Jupyter with `cao-points-analysis.ipynb` using code `Jupyter Notebook`.   
4. Copy code in cmdr if page does not load automatically.

Here is how to run the `pyplots.ipynb` notebook:
1. Open cmdr terminal.
2. Go to notebook location.
3. Run Jupyter with `pyplot.ipynb` using code `Jupyter Notebook`.   
4. Copy code in cmdr if page does not load automatically.



### Explore

Have a look at the two notebooks in this repo in Jupyter.
Some interesting aspects for `pyplot.ipynb`:

- The notebook `plots.ipynb` has three difference plot types as examples. You can edit the parameters of the plots to see different effects.

Change the following code (numbers and colours) and see how the plot changes in respect to its appearance:

```python
line_props = dict(alpha=0.7)
boxprops = dict(linestyle='dashdot', linewidth=3, color='blue')
flierprops = dict(marker='o', markersize=10, markerfacecolor = 'y', markeredgecolor='black' )
# Let's plot
plt.figure(figsize=(18,10))
with plt.style.context('seaborn'):
    data_updated = data[['sepal_length', 'sepal_width', 'petal_length', 'petal_width']]
    # set properties for fliers, box and whiskers. Changed width of boxes.
    plt.boxplot(data_updated, labels = ('sepal_length', 'sepal_width', 'petal_length', 'petal_width'),
               whiskerprops = line_props, boxprops = boxprops, flierprops = flierprops, widths = 0.4 ) 
    plt.suptitle('Boxplot of Iris Fisher Data Variables') # add title
    plt.xlabel('Variable') # x axis label
    plt.ylabel('cm') # y axis label
```

Some interesting aspects for `cao-points-analysis.ipynb`:

- The notebook `cao-points-analysis.ipynb` contains a detailed analysis of CAO points from 2019-2021.
- Some courses contain no data which is clearly an error on the CAO team's part. 
- We have delved into 'points differences' in the certain courses over a period of years which is very informative.
- There is a wealth of information to be gleaned from these datasets. For example, the parameters in a lot of code can be altered to display difference results. The following code can be easily altered to compare difference parameters:
```python
# Let's look at the value differences between some courses in this dataframe
# Let's convert our Points_R1_2021 column to a float as it is currently an 'object'
level_seven_clean['Points_R1_2021']= pd.to_numeric(level_seven_clean['Points_R1_2021'], errors='coerce').astype('float')
# Code to find the difference in values between EOS and Mid [25]
level_seven_clean['Val_Diff'] = level_seven_clean['Points_Mid_2019'] - level_seven_clean['Points_R1_2021']
# Let's display our result
level_seven_clean.sort_values('Val_Diff', ascending = False).head(15)
```
  


### Credits

####

I heavily relied on StackOverflow for solving many issues in the generation of the two notebooks. You can find the main homepage here for Python queries: [StackOverflow](https://stackoverflow.com/questions/tagged/python)





## Troubleshooting
```python

import warnings
warnings.filterwarnings("ignore")
```
The warning package was incorporated into the notebooks in order to allow to following code to execute with no warning message. The code executed fine, this was just with the appearance in mind.


## Conclusion

The notebooks contained in this repository serve as a great resource into various aspects of coding: 
- The use of `python` and `jupyter`
- The use of `pandas`, `numpy` and `matplotlib`
- Overview of functionalities of plotting

These aspects are the foundation of good programming and therefore this repository can be consulted at any stage. The `pyplot.ipynb` and `cao=points-analysis.ipynb` noteboos have taken a dataset, prepared it for analyses and then plotted results i.e the whole process flow we would meet in industry when given a dataset to analyse.

## References
CAO-Points
1. https://www.cao.ie/ 
2. http://www.cao.ie/index.php?page=points&p=2021  
3. https://docs.python-requests.org/en/latest/
4. https://docs.python.org/3/library/datetime.html
5. https://docs.python.org/3/library/re.html
6. https://automatetheboringstuff.com/chapter8/
7. https://pandas.pydata.org/
8. https://docs.python.org/3/library/urllib.html
9. https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.iloc.html
10. https://pandas.pydata.org/pandas-docs/stable/user_guide/merging.html
11. https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop_duplicates.html
12. https://pandas.pydata.org/docs/reference/api/pandas.concat.html
13. https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.join.html
14. https://thispointer.com/python-pandas-count-number-of-nan-or-missing-values-in-dataframe-also-row-column-wise/
15. https://stackoverflow.com/questions/39128856/python-drop-row-if-two-columns-are-nan
16. https://stackoverflow.com/questions/35465741/pandas-convert-column-with-empty-strings-to-float
17. https://www.analyticsvidhya.com/blog/2021/05/a-comprehensive-guide-to-data-analysis-using-pandas-hands-on-data-analysis-on-imdb-movies-data/
18. https://stackoverflow.com/questions/11285613/selecting-multiple-columns-in-a-pandas-dataframe
19. https://realpython.com/pandas-plot-python/#survey-your-data
20. https://plotly.com/python/subplots/
21. https://pandas.pydata.org/docs/getting_started/intro_tutorials/03_subset_data.html
22. https://www.datasciencemadesimple.com/return-first-n-character-from-left-of-column-in-pandas-python/
23. https://www.geeksforgeeks.org/plot-a-pie-chart-in-python-using-matplotlib/
24. Python for Data Analysis: Data Wrangling with Pandas, NumPy, and IPython. Wes McKinney. ISBN-13: 978-1491957660 ISBN-10: 1491957662
25. https://stackoverflow.com/questions/48350850/subtract-two-columns-in-dataframe.
26. Automate the Boring Stuff with Python: Practical Programming for Total Beginners. Al Sweigart.  ISBN-13: 978-1593275990 ISBN-10: 1593275994

Matplotlib
1. https://morioh.com/p/9860e0021ad9
2. https://stackoverflow.com/questions/58185487/how-to-read-csv-file-into-jupyter-notebook
3. Marshall, Michael 2019. Iris Data Set. Available from: http://archive.ics.uci.edu/ml/datasets/Iris
4. Python Data Science Handbook. Jake VanderPlas. ISBN: 9781491912058
5. https://www.activestate.com/resources/quick-reads/what-is-matplotlib-in-python-how-to-use-it-for-plotting/
6. Python and Matplotlib Essentials for Scientists and Engineers. Matt A Wood. Online ISBN: 978-1-6270-5620-5
7. Matplotlib for Python Developers. Sandro Tosi. ISBN: 9781847197900
8. https://realpython.com/python-matplotlib-guide/
9. https://numpy.org/doc/stable/reference/random/index.html
10. https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html#module-matplotlib.pyplot
11. https://htmlcolorcodes.com/
12. https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html#matplotlib.pyplot.plot
13. https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.normal.html#numpy.random.Generator.normal
14. https://matplotlib.org/stable/api/_as_gen/matplotlib.axes.Axes.annotate.html
15. https://matplotlib.org/stable/tutorials/introductory/customizing.html
16. https://jakevdp.github.io/PythonDataScienceHandbook/04.11-settings-and-stylesheets.html
17. https://matplotlib.org/stable/tutorials/introductory/customizing.html
18. https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.axvline.html
19. https://pandas.pydata.org/docs/reference/api/pandas.Series.value_counts.html
20. https://www.geeksforgeeks.org/box-plot-in-python-using-matplotlib/
21. https://www.analyticsvidhya.com/blog/2020/02/beginner-guide-matplotlib-data-visualization-exploration-python/
22. https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.boxplot.html#matplotlib.pyplot.boxplot
23. https://www.dummies.com/education/math/statistics/what-a-boxplot-can-tell-you-about-a-statistical-data-set/
24. https://www.khanacademy.org/math/cc-sixth-grade-math/cc-6th-data-statistics/mean-and-median/v/statistics-intro-mean-median-and-mode#:~:text=The%20mean%20(average)%20of%20a,ordered%20from%20least%20to%20greatest.
25. https://sodocumentation.net/matplotlib/topic/6368/boxplotshttps://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_numpy.html
26. 


README
1. https://www.dataquest.io/blog/jupyter-notebook-tutorial/
2. https://morioh.com/p/9860e0021ad9


## Contact

***
Conor McCaffrey
[cmcaff@outlook.com](mailto:cmcaff@outlook.com)