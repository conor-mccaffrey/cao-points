# cao-points
# Remove commas, to remove tage  <[^>]*> in CTRL H    
# Remove Headings and go tos...
# Download file, remove tags,
# Python regular expression library helps with datasets
# File is really 3 fields (for CSV format). AL801, NameofCourse, Points
# Use regular expression to match stuff , not just delete. 
# Look 20 mins into video for instructions  
# Learn regular expressions


# Compile the regular expression for matching lines.
re_course = re.compile(r'([A-Z]{2}[0-9]{3})  (.*)([0-9]{3})(\*?) *') # the .* is filler, can be basically anything. we are using it for the course name and spaces at end
# the 'r' at front means 'raw'. If you put at front it means 'dont evaluate backslashes'. Treat as a raw string
# (\*?) Asterik means 'zero or more of'. + means 1 or more of. "88*", asterik applies to second 8. this meams "8+" one or more eights
# (\*?) Backslah means dont treat asterik as a quantifer, treat as a backslash. Question mark is the quantifier, it means zero or one of.
 # Space with asterik means any number of spaces
#
#
#
#
#Two columns of figures appear after each course in this year's CAO spread which you can download here. The first column gives the FINAL CUT-OFF points, in other word, the points score achieved by the last applicant being offered a place on that course in 2008.

The second column gives the MID figure, that is, the points score of the applicant midwaybetween the highest and the lowest applicant being offered a place.
#
#ff
#
#
#


References
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