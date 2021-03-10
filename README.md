# Super Bowl Ad Analysis

## Introduction
  
This project goes through my process of analyzing 244 Super Bowl Adverisements from the 2000 - 2020 Super Bowls.  Super Bowl Ads are the pinnacle of advertising and marketing, these companies put everything into these ads in hopes of generating interest & awareness for their brand.  In 2021 the price of a 30-second time slot was $5.5 million, and most of these companies don't just buy 1.  I was interested in exploring an advertising dataset such as this one and seeing what kind of insights and takeaways I could get from exploring the data.

## The Data
The dataset comes from [fivethirtyeight](https://projects.fivethirtyeight.com/super-bowl-ads/), where they analyzed 244 ads from the 10 most popular Advertisers for the Super Bowl (including the NFL).  Fivethirtyeight created characteristics of every ad, like if it was funny or if it included a celebrity, and opted to share their dataset along with their own findings.

This dataset is obviously biased.  It doesn't include every advertisement that's been shown, and it only includes the same companies year after year.  However, I still think there are trends and insights available in the data that are meaningful enough to learn something from despite the bias.  Below are the variables provided in the dataset.

Categorical Variables      | Continuous Variables    
-------------------------- | ---------------------- 
Brand | Year  
Funny               | Youtube Views
Animals           | Youtube Likes
Use Sex         | Youtube Dislikes
Danger  | 
Show Product Quickly          | 
Patriotic
Celebrity

## Exploratory Data Analysis

I started by looking at how many commercials each of these companies have produced for the Super Bowl in the last 20 years.  You can see clear trends of the kinds of companies who are most likely to advertise for the biggest event of the year.  Beer companies, snack companies, and automotive companies make up the bulk of the business.



I used a package called ExPanDaR, which goes through an automated exploratory phase and produces a couple simple graphs of relationships in the data.  This violin chart helps show when each of the companies started advertising in the Super Bowl.  You can see companies like Bud Light and Budweiser have been there since the beginning.  However, I found this interesting article that explained that Budweiser didn't actually advertise in this past 2021 Super Bowl.



This was another graph provided by ExPanDaR.  It's showing how certain companies might use some characteristics more than others, like Doritos using humor in the vast majority of their advertisements.  Bud Light is up there as well, whereas a direct competitor in Budweiser is considerably less likely to use humor.  You can look at these graphs for all the characteristics and compare them across companies, which might be useful if you worked for a similar kind of company and wanted to analyze the kinds of characteristics they use in their advertising.  



The most interesting graph comes from looking at the characteristic distributions from the last 20 years.  You can see how using sex appeal was very popular in the early 2000s, but has recently fallen completely off as an advertising strategy.  Recently, we're seeing a lot more use of celebrities in commercials.



I wanted to get a better idea of how the pricing for these time slots has changed over the past years.  superbowl-ads.com offered a simple dataset dating back to 1968.  The biggest increase in pricing came around 2000, which apparently was the result of the Dot-com bubble which saw a bunch of new competition come into the Super Bowl advertising scene with companies trying to generate buzz for their websites.

The price for a 30-sec slot was increasing every year since 2010, but went down for the 2021 Super Bowl likely due to the effects of the pandemic.



## Insights


![sb_plot6](https://user-images.githubusercontent.com/16946556/110707969-e74fee80-81ae-11eb-8bdf-ba6dae8d6d6f.png)
![sb_plot5](https://user-images.githubusercontent.com/16946556/110707973-e7e88500-81ae-11eb-934b-fdde893960bb.png)
![sb_plot3](https://user-images.githubusercontent.com/16946556/110707974-e7e88500-81ae-11eb-8016-21c46014f54f.png)
![sb_plot2](https://user-images.githubusercontent.com/16946556/110707975-e8811b80-81ae-11eb-9dbd-27e2df0e13aa.png)
![sb_plot4](https://user-images.githubusercontent.com/16946556/110707977-e8811b80-81ae-11eb-929f-bab2747a7ee1.png)
![sb_plot9](https://user-images.githubusercontent.com/16946556/110708079-0cdcf800-81af-11eb-92eb-53d008f77024.png)
![sb_plot1](https://user-images.githubusercontent.com/16946556/110707979-e8811b80-81ae-11eb-857f-e1f37eb76cad.png)
![sb_plot8](https://user-images.githubusercontent.com/16946556/110707980-e919b200-81ae-11eb-961c-2f3a35b745e3.png)
![sb_plot7](https://user-images.githubusercontent.com/16946556/110707981-e919b200-81ae-11eb-84a8-a72fcc3bb3d4.png)

