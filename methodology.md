# **Methodology**

## **Data Sources**

- **Coffee Origins:** There are hundreds of factors that go into producing the perfect coffee bean, and this [dataset ](coffee.csv) covers it all for a wide variety of beans. Detailing coffee bean type, area of origin, and important geographical information like altidue. Beans are also classifed by their region and owner coupled with various ratings scores across several factors like acidity, sweetness, flavor and aftertaste.

- **Speciality Coffee:** The Speciality Coffee Association developed a [coffee cupping socre](https://nerdjava.co/specialty-cup-score/?srsltid=AfmBOopFYJzcq5qGGH6PWeonyKtTn3lmcludW_d91kgzAvYISu6MYAYM) ranging from 0 to 100. A scroe of 80 or above gets the badge of honor known as the "speciality coffee." Any coffee below that benchmark is considered Commercial-grade coffee.

- **Altitude:** Every coffee bean you buy in a store comes with an [altitude classification](https://www.stokedroasters.com/blogs/news/coffee-guide-altitudes-affect-on-beans?srsltid=AfmBOopQ2AWq_wmvzA1HyfgORmxws2qFYV_cSuG8J_WBAOELAZBghEYT) on the packaging. Have you ever wondered why? Well altitude has a huge influence on the production of coffee beans infleucing factors like acidity and flvor.

## **Data Preparation/Cleaning**

### Country Organization and Average Score Calculation

Geographical location plays a huge role in the outcome of a coffee beans flavors, and processing methods, which affects its speciality score. To explore the effect of geogrpahical location on average speciality score I began by writing a function to loop through my dataset and create a list of all the unique countries that have a coffee bean in the dataset.

Now that I know all the countries I need to find a score for, I can sort through the total scores of the coffee. This part required more detailed data processing. I decided to write a function that will take in a country and a dataset and, calculate the average speciality score for that country. The function involved parsing through the dataset line by line and checking if the first column was equal to the country we are searching for. If true I would find the column with the total score, and convert it to a float for decimal accuracy. Then I would add it to a total score variable. I also kept a count of how many different beans were associated with each country. After parsing through the whole dataset I can find the average total score for that country by calculating $$\frac{Total Score}{Count}$$

To efficiently store this data for each country I decided to create a dictionary using the country as the key and its average speciality score as the value. The dictionary makes it wasy to look up the speciality score for any country.

### Altitude Grouping

There are too many unique altitudes to graph them all with their corresponding acidity and flavor scores. In order to clean up the data I decided to group entries into certain altitude bounds namely, **very low** ($<2000ft$), **low** ($2000ft-2500ft$), **medium** ($2500ft-3000ft$), **high** ($3000ft-4000ft$) and **very high** ($>4000ft$). Once I made groupings I created new dataframes for each altitude grouping using:

```python
very_low_altitude = data.loc[coffee["Altitude"] < 2000]
```

From there I can create my double-bar chart by pulling data from each altitude dataframe.

### Flavor and Aftertaste Data

The beauty of a scatter plot is letting the pure numerical data tell the story for you. The only data clean up I had to perform was ensuring there were no 0 or Nan values to skew data. After removing these values I could plot the flavor and aftertaste for each coffee bean in the dataset.

## **Assumptions**

- Assumptions: Decisions you made during your data analysis about how you would interpret the data that may or may not have been consistent with the logic behind the individuals who collected the data. For example, perhaps you're assuming the date December 2023 is 12/1/2023.

## **Limitations**

The dataset of coffee beans contains mainly speciality coffee beans with a few commercial grade beans. This means all my data comparison is ranking and analyzing the best of the best when it comes to coffee beans. This information might not be useful to he average coffee drinker who buys whatever coffee they can find in a store. A larger dataset with beans all the way from low commercial grade to the top speciality beans, can give a better picture and comparison for all types of coffee drinkers.
