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
  
![](https://miro.medium.com/max/481/1*zhXyt_vc04KTPHLCU2Yf8Q.png)

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

![](https://cdn.journaldev.com/wp-content/uploads/2020/05/area-plot-in-r.png)

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

![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Histogram_of_arrivals_per_minute.svg/1200px-Histogram_of_arrivals_per_minute.svg.png)

------
## Bar Charts.
- A bar chart also known as a bar graph is a type  of plot where the length of each bar is proportional to the value of the item that it represents.
- It is commonly used to compare the values of a variable at a given point of time. 
- Creating Bar Charts.
  - import matplotlib as mpl
  - import matplotlib.pyplot as plt
  - years = list(map(str,range(1980,2014)))
  - df_iceland = df_canada.loc['Iceland',years]
  - df_iceland.pyplot(kind='bar')
  - plt.title('Icelandic Immigration to Canada from 1980 to 2013')
  - plt.xlabel('Year')
  - plt.ylabel('Number of immigrants')
  - plt.show()
  
  ![](https://chartio.com/assets/dfd59f/tutorials/charts/grouped-bar-charts/c1fde6017511bbef7ba9bb245a113c07f8ff32173a7c0d742a4e1eac1930a3c5/grouped-bar-example-1.png)
------  
## Pie Charts.
- A pie chart is a circular statistical graphic divided into slices to illustrate numerical proportion.
- Creating Pie Chart.
- To group our data by continent using the continent column, and we use pandas for this.
  - df_continents = df_canada.groupby('Continents',axis=0).sum()
- Now, using matplotlib we do it as follows.
  - import matplotlib as mpl
  - import matplotlib.pyplot as plt
  - df_continents['Total'].plot(kind='pie')
  - plt.title('Immigration to Canada by Continent[1980-2013]')
  - plt.show()
- Bar charts are much more better than Pir charts.

![](https://www.mathsisfun.com/data/images/pie-chart-movies.svg)

------
## Box Plots.
- A box plot is a way of statistically representing the distribution of given data through five main dimensions, i.e. minimum, first quartile, median, third quartile, maximum.
- Creating Box Plots.
  - import matplotlib as mpl
   - import matplotlib.pyplot as plt
   - df_japan = df_canada.loc[['Japan'],[years].transpose()
   - df_japan.plot(kind='box')
   - plt.title('Box plot of Japanese immigrants from 1980 to 2013')
   - plt.ylabel("Number of immigrants")
   - plt.show()
 ![](https://www.simplypsychology.org/boxplot.jpg)  
------
## Scatter Plots.
- A scatter plot is a type of plot that displays values pertaining to typically two variables against each other.
- Creating Scatter Plots.
  - import matplotlib as mpl
  - import matplotlib.pyplot as plt
  - df_total.plot(kind='scatter', x='year', y='total')
  - plt.title('Total immigrant population to canada from 1980 to 2013')
  - plt.xlabel('Year')
  - plt.ylabel('Number of Immigrants')
  - plt.show()
- The scatter plot clearly depicts an overall trend of the given plot with time.

![](https://www.learnbyexample.org/wp-content/uploads/r/typical-scatter-plot.png)

------
## Waffle Chart.
- A waffle chart is a great way to visualize data in relation to a whole or to highlight progress against a given threshold.
- It is normally created to display progress towards goals.
- Here the contribution of each country is transformed into a number of tiles that is proportional to the country's contribution to the total, so that more the tiles, resulting in what resembles a waffle resembles a waffle when combined.
![](https://vizartpandey.com/wp-content/uploads/2019/08/Waffle-Chart.png)
------
## Word Cloud.
- A word cloud is simply a depiction of the importance of different words in the body of the text.
- The more a specific word appears in a source of textual data the bigger and bolder it appears in the word cloud.
![](https://lh3.googleusercontent.com/proxy/n2ZbeRiIP3boqkutSSBpR6u53HTvXXWmXS4o96ptwRTgJTGLntMl-lEvBgIqDEOxw4l9oJ2gv2ePlUpqUEzZvoYtK3_YuvKL2Uo-tWO13vN1l5N5UtO9KV5FIHLVKvF2qnrtDxNRhauI3cGNcU7isGxPVJU)
------
## Seaborn.
- Seaborn is a python visualization library based on Matplotlib. It is build to provide a high level interface for drawing attractive statistical graphics, such as Regression plots, Box plots and so on.
- With Seaborn we can generate plots with code that is 5 times less than with Matplotlib.
- Creating Seaborn.
  - import seaborn as sns
  - ax = sns .regplot(x='year',y='total',data=df_tot)
- The above is the code of scatter plot with a regression line and also with 95% confidence level.
- Using the color and marker parameter, we can change the colour and marker too.
![](https://miro.medium.com/max/2060/1*3VgCwcZraA0u5hMHpRhJcw.png)
------
## Folium.
- Folium is a powerful data visualization library in python that was built to visualize geospatial data.
- By knowing the latitude and longitude values, we can create a map of any location of any type.
- Creating a map of Canada.
  - world map=folium.Map(
  - location=[56.130, -106.35]'
  - zoom_start=4, tiles='StamenToner')
  - world_map
- We can also create a marker using feature group, as a red point on the current location.
![](https://miro.medium.com/max/1105/1*tlsecoIK9kErqqrlvstBuQ.jpeg)
------
## Choropleth Map.
- A Choropleth map is a thematic map in which areas are shaded or patterned in proportion to the, measurement of the statistical variable being displayed on the map.
- The higher the measurement, the darker is the colour.
- In order to create a choropleth map of a region of interest, Folium requires a Geo JSON file that includes geospatial data of the region.
- Creating a map.
  - world_map = folium.Map(
  - zoom_start = 2, titles='Mapbox Bright')
  - world_geo= = r'world_countries.json'
  - world_map.choropleth(
  - geo_path = world_geo
  - data=df_canada,
  - columns=['Country','Total']
  - key_on='features.properties.name',
  - fill_color='LOrRD',
  - legend_name='Immigration to Canada')
  - world_map
  
![](https://datavizcatalogue.com/methods/images/top_images/choropleth.png)  
