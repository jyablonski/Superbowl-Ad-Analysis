# Super Bowl Ad Analysis

## Introduction
  
This project goes through my process of analyzing 244 Super Bowl Adverisements from the 2000 - 2020 Super Bowls.  Super Bowl Ads are the pinnacle of advertising and marketing, these companies put everything into these ads in hopes of generating interest & awareness for their brand.  In 2021 the price of a 30-second time slot was $5.5 million, and most of these companies don't just buy 1.  I was interested in exploring an advertising dataset such as this one and seeing what kind of insights and takeaways I could get from exploring the data.

## The Data
The dataset comes from [fivethirtyeight](https://projects.fivethirtyeight.com/super-bowl-ads/), where they analyzed 244 ads from the 10 most popular Advertisers for the Super Bowl (including the NFL).  Fivethirtyeight created characteristics of every ad, like if it was funny or if it included a celebrity, and opted to share their dataset along with their own findings.

This dataset is obviously biased.  It doesn't include every advertisement that's been shown, and it only includes the same companies year after year.  However, I still think there are trends and insights available in the data that are meaningful enough to learn something from despite the bias.  Below are the variables provided in the dataset.

Categorical Variables      | Continuous Variables    
-------------------------- | ---------------------- 
Brand | Year  
Funny               | 
Animals           | 
Use Sex         | 
Danger  | 
Show Product Quickly          | 
Patriotic
Celebrity

## Exploratory Data Analysis

I started by looking at how many commercials each of these companies have produced for the Super Bowl in the last 20 years.  You can see clear trends of the kinds of companies who are most likely to advertise for the biggest event of the year.  Beer companies, snack companies, and automotive companies make up the bulk of the business.

![sb1](https://user-images.githubusercontent.com/16946556/107553049-1b70c900-6b89-11eb-973d-2af29f0f17ec.png)

![sb4](https://user-images.githubusercontent.com/16946556/107553041-1ad83280-6b89-11eb-9880-57e24e1db415.png)

I used a package called ExPanDaR, which goes through an automated exploratory phase and produces a couple simple graphs of relationships in the data.  This violin chart helps show when each of the companies started advertising in the Super Bowl.  You can see companies like Bud Light and Budweiser have been there since the beginning.  However, I found this interesting article that explained that Budweiser didn't actually advertise in this past 2021 Super Bowl.

![sb6](https://user-images.githubusercontent.com/16946556/107553051-1c095f80-6b89-11eb-8bb7-e3c585c65398.png)

![sb7](https://user-images.githubusercontent.com/16946556/107553050-1c095f80-6b89-11eb-9e5f-3e7871f123b9.png)

![sb3](https://user-images.githubusercontent.com/16946556/107553043-1ad83280-6b89-11eb-9d29-a68bc57cb198.png)

The most interesting graph comes from looking at the characteristic distributions from the last 20 years.  You can see how using sex appeal was very popular in the early 2000s, but has recently fallen completely off as an advertising strategy.  Recently, we're seeing a lot more use of celebrities in commercials.

![sb2](https://user-images.githubusercontent.com/16946556/107553046-1b70c900-6b89-11eb-8d07-8a97b6bbd12a.png)

I wanted to get a better idea of how the pricing for these time slots has changed over the past years.  superbowl-ads.com offered a simple dataset dating back to 1968.  The biggest increase in pricing came around 2000, which apparently was the result of the Dot-com bubble which saw a bunch of new competition come into the Super Bowl advertising scene with companies trying to generate buzz for their websites.

The price for a 30-sec slot was increasing every year since 2010, but went down for the 2021 Super Bowl likely due to the effects of the pandemic.

![sb5](https://user-images.githubusercontent.com/16946556/107553039-1a3f9c00-6b89-11eb-8760-833edc568b81.png)


## Insights
Advertising in the Super Bowl must be working for most of these companies, because it comes at a steep price.  
