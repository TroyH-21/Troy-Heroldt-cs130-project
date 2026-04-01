# Idea Dump

## Potential Project Datasets:

### [Coffee Data](https://corgis-edu.github.io/corgis/csv/coffee/)

Data of Arabica and Robusta beans, across countries and their professional rating on a 0-100 scale.

**Questions:**

1.  What country produces the best rated coffee and how its climate is suited for growing coffee beans?

**Answer:**

I will write a function **avg_total_coffee_score(country)**, that accepts a **country** paramater. The fucntion will loop through the .csv file and check if the coffee bean entry is from **country**. If it is it will add it to a **total_score** variable and up the **count** by one. At the end of the loop it will find countries average total score by calculating **total_score/country**.

I can create a list that contains every countries name only once and run a loop on the **avg_total_coffee_score(country)** function to get an average total score of every country, and save each average total score to a list.

I now have to lists with all the results I need (country name, average total score). I can use those two lists to then display a table showing each country and its average _**Data.Scores.Total**_ and rank them from 1-n. I will then use geographical and weather data from another source and analyze what factors make certain countries better for growing coffee beans compared to another and how that is relfected in the average _**Data.Scores.Total**_

2.  Which factor, flavor, aftertaste or sweetness, inlfuences the overall coffee score the most?

### [Video Game Data](https://corgis-edu.github.io/corgis/csv/video_games/)

Details the sales, rating and playtime of over a thousand video games released between 2004 and 2010.

**Questions:**

1. What video game takes the longest time to complete?
2. What video game has the best resell value, and is nostalgia the reason?
