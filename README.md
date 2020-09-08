# Data-Visualization-with-Python.
- Data Visualization is a way to show a complex data in the form that is graphical, easy to understand more effective, attractive and impactive.
  - It is used for:
  1. Exploratory data analysis.
  2. Communicate data clearly.
  3. Shared unbiased representation of data.
  4. Use them to support recommendations to different stakeholders.
  - When creating a visual, always remember:
  1. Less is Effective.
  2. Less is more Attractive.
  3. Less is more Impactive.
  - The above 3 points are given by Darkhorse Analytics.
------
## Matplotlib.
- It is one of the most widely used, if not the most popular data visualization library in Python. It was created by John Hunter, an neurobiologist. Matplotlib was originally developed as an ECoG visualization tool, and just like MATLAB, Matplotlib was equipped with a scripting interface for quick and easy generation of Graphics represented by Pyplot.
- It composed of 3 main layers, the back-end layer, the artist layer and the scripting layer.
1. Backend Layer: It has 3 build-in abstract interface classes.
  - Figure Canvas: Encompasses the area onto which the figure is drawn.
  - Renderer: Knows how to draw on the Figure Canvas.
  - Event: Handles user inputs such as keyboard strakes and mouse clicks.
2. Artist Layer: It comprises of one main object-Artist. There are 2 types of artist objects.
  - Primitive: Line 2D, Rectangular, Circle and Text.
  - Composite: Axis, Tick, Axes and Figure.
- Each composite artist may contain other composite artists as well as primitive artists.
3. Scripting layer: Comparised mainly of pyplot, a scripting interface that is lighter that the Artist layer. It is used by the scientists who are not professional programmers.
------
## Using Matplotlib.
- import matplotlib.pyplot as plt
- plt.plot(5,5,'o')
- plt.show()
- It will print a dot on(5,5) on the browser. If the plot is generating in a new window, then you can enforce generating plots within the browser, using a magic function. It starts with % Matpotlib, i.e. % matplotlib inline. Here inline is used as an backend.
- Pandas also has built-in implementation of matplotlib.
------
## Dataset.
- In this learning we will be using the following dataset.
- The population division of the United Nations compiled data pertaining to 45 countries. For each country, annual data on the flows of international migrants is reported in addition to other metadata. We will primarily work with a United Nations data on immigrations to Canada.
------
## Read Data into Pandas Dataframe.
- import numpy as np
- import pandas as pd
- from_future_import print_function
- #pip install.xlrd
- print("xlrd installed")
- df_can = pd.read_excel
- (https:// ------||------ (link of excel file)
- sheetname = "Canada by Citizenship",
- skiprows = range(20),
- skip_footer = 2)
- By using the head() function you can see the first 5 rows of dataframe, i.e. df_can.head().
------
## Line Plots.
- A line plot is a type of plot which displays information as a series of data points called 'markers' connected by straight line segments.
- It is generally used when we have a continuous dataset and we are interested in visualizing the data over a period of time.
- Creating Line Plots.
  - import matplotlib as mpl
  - import matplotlib.pyplot as plt
  - years = list(map(str,range(1980,2014)))
  - df_canada.loc['Haiti',years].plot
  - plt.title('Immigration from Haiti')
  - plt.ylabel('Number of Immigrants')
  - plt.xlabel('Years')
  - plt.show()
------
## Area Plots.
- An area plot known as an area chart or graph is a type of plot that depicts accumulated totals using numbers or percentages over time.
- It is generally used when we are trying to compare two or more quantities. It is based on line plot.
- Creating Area Plots.
  - To sort our dataframe in decending order we used sort_values function.
  
  - years = list(map(str,range(1980,2014)))
  - df_canada.sort_values(['Total'])
  - ascending = False, axis=0, inplace = True
  - df_top5 = df_canada.head()
  - df_top5 = df_top5[years].transpose()
  
- Now, we can plot the area plot by calling the plot function on dataframe.
  
  - import matplotlib as mpl
  - import matplotlib.pyplot as plt
  - df_top5.plot(kind = 'area')
  - plt.title("Immigration trend of top 5 countries")
  - plt.ylabel('Number of immigrants')
  - plt.xlabel('Years')
  - plt.show()
  
- Here, we have generated the area plot using the inline backend.
  ------
## Histograms.
- A Histogram ia a way of representing the frequency distribution of a variable.
- Creating Histogram.
  - import matplotlib as mpl
  - import matplotlib.pyplot as plt
  - df_canada['2013'].plot(kind='hist')
  - plt.title('Histograms of Immigration from 195 countries in 2013')
  - plt.ylabel('Number of countries')
  - plt.xlabel('Number of Immigrants')
  - plt.show()
-  By importing numpy library, we can make our Histogram easy to read.

