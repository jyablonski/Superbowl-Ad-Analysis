# Super Bowl Ad Analysis

## Introduction
  
This project goes through my process of analyzing 247 Super Bowl Adverisements from the 2000 - 2020 Super Bowls.  Super Bowl Ads are the pinnacle of advertising and marketing, with the price of a 30-second time slot being $5.5 million in this past Year's Super Bowl.  Few companies have the budget to be able to afford a price tag like that, and you have to imagine the amount of prep that goes into creating a Commercial for that kind of magnitude.  I was interested in exploring an advertising dataset such as this one and seeing what kind of insights and takeaways I could get from exploring the data in further depth.

## The Data

The dataset originally from [fivethirtyeight](https://projects.fivethirtyeight.com/super-bowl-ads/), and later became part of a [Tidytuesday Project](https://github.com/rfordatascience/tidytuesday) for users of the R Community.  Fivethirtyeight analyzed 247 ads from the 10 most popular Advertisers for the Super Bowl, and created characteristics of every ad such as if it was funny or if it included a celebrity, and Tidytuesday utilized Youtube's API to add various Youtube-specific data metrics along to the dataset.

This dataset is obviously biased.  It doesn't include every advertisement that's been shown in the included Super Bowls, and it only includes the same companies year after year.  However, I still think there are trends and insights available in the data that are meaningful enough to learn something from despite the bias.  Below are the variables provided in the dataset.

Categorical Variables      | Continuous Variables    
-------------------------- | ---------------------- 
Brand | Year  
Funny               | Youtube Views
Animals           | Youtube Likes
Use Sex Appeal        | Youtube Dislikes
Danger  | 
Show Product Quickly          | 
Patriotic
Celebrity

I Utilized R to work on this project, along with the dplyr, ggplot2, tidytext, and skimR packages.

## Exploratory Data Analysis

I started by looking at how many commercials each of these companies have produced for the Super Bowl in the last 20 years.  You can see clear trends of the kinds of companies who are most likely to advertise for the biggest event of the year. 
  * Beer, snack, and automotive companies make up the bulk of returning advertisers.
  * These companies are buying multiple ad slots every year.  These costs can range anywhere between $20-45 million dollars.

![sb_plot3](https://user-images.githubusercontent.com/16946556/110707974-e7e88500-81ae-11eb-8016-21c46014f54f.png)

This year-by-year graph helps show the # of commercials these 9 companies are getting every year.  While the exact amount of commercials fluctuates every year, it's clear these 9 companies are getting the bulk of the business.

![sb_plot6](https://user-images.githubusercontent.com/16946556/110707969-e74fee80-81ae-11eb-8bdf-ba6dae8d6d6f.png)

Here is a breakdown of all of the ad characteristics, grouped by brand.  We can easily see the similarities & differences in what elements these comapnies put in their ads in order to get their brand to resonate with viewers.
  * Funny and Show Product Quickly are the 2 most popular characteristics these companies utilize.  This is something worth exploring in further detail later on.

![sb_plot8](https://user-images.githubusercontent.com/16946556/110707980-e919b200-81ae-11eb-961c-2f3a35b745e3.png)

I also wanted to look at the Youtube data for the commercials to see if anything stood out.  While most of these companies have a similar Dislike % across all of their videos, you can see there are a number of outliers, including a [Bud Light commercial](https://www.youtube.com/watch?v=hkSQ2Vr41bM) with a Dislike % greater than 60%!  

![sb_plot1](https://user-images.githubusercontent.com/16946556/110707979-e8811b80-81ae-11eb-857f-e1f37eb76cad.png)

Something else that was interesting was the fluctutation in average Youtube Views per year for these Super Bowl commercials.  There didn't seem to be a logical reason why there were such large spikes in some of these years.  [This Doritos commercial](https://www.youtube.com/watch?v=6SWNLDdnz0A) has over 170 million Youtube views and was the most popular commercial in the dataset.

![sb_plot2](https://user-images.githubusercontent.com/16946556/110709113-9214dc80-81b0-11eb-8dc7-d0e819398fb2.png)

This is a heatmap looking at the % of Commercials each brand uses these ad characteristics in.  
  * The more red, the higher % chance the company uses that characteristic.

![sb_plot9](https://user-images.githubusercontent.com/16946556/110708079-0cdcf800-81af-11eb-92eb-53d008f77024.png)

The most interesting graph comes from looking at the characteristic distributions from the last 20 years.  
  * You can see how using sex appeal was very popular in the early 2000s, but has recently fallen completely off as an advertising strategy.  
  * Recently, we're seeing a lot more use of celebrities in commercials.

![sb_plot5](https://user-images.githubusercontent.com/16946556/111010781-5e6eb980-834c-11eb-9db3-8c2a05bc7f7f.png)


I wanted to get a better idea of how the pricing for these time slots has changed over the past years.  superbowl-ads.com offered a [simple dataset](https://superbowl-ads.com/cost-of-super-bowl-advertising-breakdown-by-year/) dating back to 1968.  

The biggest increase in pricing came around 2000, which apparently was the result of the Dot-com bubble which saw a bunch of new competition come into the Super Bowl advertising scene with companies trying to generate buzz for their websites.
  * The price for a 30-sec slot was increasing every year since 2010, but went slightly down for the 2021 Super Bowl due to the effects of the pandemic.

![sb_plot7](https://user-images.githubusercontent.com/16946556/110707981-e919b200-81ae-11eb-84a8-a72fcc3bb3d4.png)


The data set came with the Youtube descriptions which you could potentially perform NLP & sentiment analysis on, but I didn't see much value in that.  Youtube descriptions vary wildly, and often include a lot of copyright infringement details or links to other social media sites & campaigns that would be hard to filter out of the actual text analysis.

## Insights & Conclusions

1. Commercials are diverse!  Companies have different views on how to conduct them, what they want out of them, and whether they are just going for brand reach & awareness or are they trying to push viewers into actively buying their product.  
    * Certain companies like Pepsi chose to incorporate celebrities into the majority of their commercials, while there were also others that used Danger & suspense to captivate the audience and keep their attention.  
    * Utilizing humor & showing the product quickly were by far the 2 most commonly used variables in these commercials.

2. It was interesting to see the use of sexual appeal get phased out in more recent years.  It was incredibly popular in the early 2000s, but wasn't utilized a single time in the 2020 Super Bowl.

3. The Intra-industry competition is intense!  Budlight vs Budweiser, Pepsi vs Coca Cola, automotive companies, phone companies, everybody wants in on the Super Bowl and getting their product out there.
    * If these companies choose not to advertise during the Super Bowl, that just means a bigger piece of the pie for their competitors.
    * This 2019 Budlight commercial which had a 64% Dislike rate included Bud Light calling out Coors Light for being made of inferior ingredients, and led to a [multi-year lawsuit](https://www.nytimes.com/2019/03/21/business/miller-lite-bud-light-lawsuit.html)


This was a fascinating project to work on and learn from.  One thing I want to try in the future is analyzing trends on Social Media such as Twitter to see the live discussion in real time and see which commercials stir the largest reactions from the average fan.  
