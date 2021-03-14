library(tidyverse)
library(extrafont)
library(skimr)
library(ExPanDaR)
library(corrplot)
library(tidytuesdayR)
library(tidytext)
library(reshape2)

# custom theme
theme_jacob <- function(..., base_size = 12) {
  theme(panel.grid.minor = element_blank(),
        panel.grid.major =  element_line(color = "#d0d0d0"),
        panel.background = element_rect(fill = "#f0f0f0", color = NA),
        plot.background = element_rect(fill = "#f0f0f0", color = NA),
        panel.border = element_blank(),
        strip.background = element_blank(),
        plot.margin = margin(0.5, 1, 0.5, 1, unit = "cm"),
        axis.ticks = element_blank(),
        text = element_text(family = "Gill Sans MT", size = base_size),
        axis.text = element_text(face = "bold", color = "grey", size = base_size),
        axis.title = element_text(face = "bold", size = rel(1.33)),
        axis.title.x = element_text(margin = margin(0.5, 0, 0, 0, unit = "cm")),
        axis.title.y = element_text(margin = margin(0, 0.5, 0, 0, unit = "cm"), angle =90),
        plot.title = element_text(face = "bold", size = rel(1.67), hjust = 0.5),
        plot.title.position = "plot",
        plot.subtitle = element_text(size = 16, margin = margin(0.2, 0, 1, 0, unit = "cm"), hjust = 0.5),
        plot.caption = element_text(size = 10, margin = margin(1, 0, 0, 0, unit = "cm"), hjust = 1),
        strip.text = element_text(size = rel(1.33), face = "bold"),
        ...
  )
}

theme_set(theme_jacob())

# loading in data ----
df <- read_csv('https://raw.githubusercontent.com/fivethirtyeight/superbowl-ads/main/superbowl-ads.csv')
ad_prices <- read_csv('superbowl_adprices.csv')
tt <- tt_load('2021-03-02')
df <- tt$youtube
 
# skimming data
skim(df)
exPanD(df)


# My analysis ----
df_brands <- df %>%
  group_by(brand) %>%
  count() %>%
  arrange(desc(n)) %>%
  ungroup() %>%
  mutate(brand = fct_reorder(brand, n))

df_new <- df %>%
  mutate(funny = funny * 1,
         show_product_quickly = show_product_quickly * 1, 
         patriotic = patriotic * 1,
         celebrity = celebrity * 1,
         danger = danger * 1,
         animals = animals * 1, 
         use_sex = use_sex * 1,
         dislike_pct = round(dislike_count / (dislike_count + like_count), 3),
         like_pct = round(like_count / (dislike_count + like_count), 3),
         brand = fct_recode(brand, Hyundai = 'Hynudai'))

df_pivot <- df_new %>%
  select(year, brand, funny:use_sex) %>%
  pivot_longer(cols = funny:use_sex,
               names_to = "characteristic",
               values_to = "count") %>%
  filter(count != 0)

# plot 1 brand boxplot
df_new %>%
  filter(!is.na(dislike_pct)) %>%
  mutate(brand = forcats::fct_reorder(brand, dislike_pct, median)) %>%
  ggplot(aes(dislike_pct, brand)) +
  geom_boxplot() +
  scale_x_continuous(labels = scales::percent) +
  labs(x = 'Dislike % (Dislikes / (Likes + Dislikes))',
       y = NULL,
       title = 'Youtube Dislikes for Super Bowl Commercials',
       subtitle = 'Do different Brands produce more polarizing Commercials?')
ggsave('sb_plot1.png', width = 8, height = 5)

# plot 2 year over year median youtube videws of commercials
df_new %>%
  filter(!is.na(view_count)) %>%
  group_by(year) %>%
  summarize(median_views = mean(view_count)) %>%
  ggplot(aes(year, median_views)) +
  geom_line() +
  geom_point(aes(size = median_views), show.legend = FALSE) +
  scale_y_continuous(labels = scales::comma) +
  labs(x = NULL,
       y = 'Median Youtube Views',
       title = 'What years were the most popular for rewatching Super Bowl Commercials on Youtube?')
ggsave('sb_plot2.png', width = 8, height = 5)

# car companies, beer & beverage & snack companies, loan and tax companies like rocket mortgage, e-trade, and intuit turbotax live.  
# curious if the superbowl was hosted during a different time of year that we'd see different types of popular ads.  
# super bowl ads are expensive, they prob spend a bulk of their budget to get attention during this 1 time per year event.  

df_pivot %>%
  group_by(characteristic) %>%
  count()

# plot 3 all 9 companies # of commercials in dataset - NFL had 11 ads.
df_brands %>%
  filter(brand != 'NFL') %>%
  ggplot(aes(n, brand)) +
  geom_col() +
  labs(x = 'Number of Commercials',
       y = NULL,
       title = 'Top 9 Companies who aired the most Super Bowl Commercials in the last 20 years')
ggsave('sb_plot3.png', width = 8, height = 5)

# plot 4 characteristics over time
df_pivot %>%
  group_by(characteristic, year) %>%
  count() %>%
  arrange(desc(n)) %>%
  ggplot(aes(n, characteristic, fill = characteristic)) +
  geom_col(show.legend = FALSE) +
  facet_wrap(~year) +
  labs(x = 'Number of Ads',
       y = NULL,
       fill = 'Characteristic',
       title = 'Ad Characteristics Distribution for the last 20 Super Bowls') +
  guides(fill = guide_legend(nrow = 1))
ggsave('sb_plot4.png', width = 8, height = 5)

df_all <- df_pivot %>%
  group_by(year, characteristic) %>%
  count()

# plot 5 characteristics over time grouped by characteristic
df_all %>%
  ggplot(aes(year, n, fill = characteristic)) +
  geom_col(show.legend = FALSE) +
  geom_smooth(show.legend = FALSE, se = FALSE) +
  facet_wrap(~characteristic) +
  labs(x = 'Year',
       y = 'Number of Commercials',
       title = 'Super Bowl Ad Trends over the last 20 years')
ggsave('sb_plot5.png', width = 8, height = 5)

yoy_commercials <- df_pivot %>%
  group_by(year) %>%
  count() %>%
  arrange(desc(n))

# plot 6 top 9 companies commericals over time.
yoy_commercials %>%
  ggplot(aes(year, n)) +
  geom_col() +
  geom_smooth(se = FALSE) +
  labs(x = NULL,
       y = 'Number of Commercials',
       title = 'Are the Big Spenders getting all the Super Bowl Ads every year ?')
ggsave('sb_plot6.png', width = 8, height = 5)

# plot 7 2021 - 5.5 million for 30 seconds.
ad_prices %>%
  ggplot(aes(year, price)) +
  geom_col() +
  geom_smooth() +
  scale_y_continuous(labels = scales::dollar_format(), breaks = c(0, 1000000, 2000000, 3000000, 4000000, 5000000, 6000000)) +
  scale_x_continuous(breaks = c(1970, 1980, 1990, 2000, 2010, 2020)) +
  labs(x = NULL,
       y = NULL,
       title = 'Price of a 30-second Super Bowl Commercial slot since 1968',
       caption = 'data via superbowl-ads.com')
ggsave('sb_plot7.png', width = 8, height = 5)

by_brand <- df_new %>%
  gather(category, value, funny:use_sex) %>%
  group_by(brand, category) %>%
  summarize(pct = mean(value)) %>%
  ungroup()

# plot 8 brand characteristics comparison
by_brand %>%
  mutate(brand = reorder_within(brand, pct, category)) %>%
  ggplot(aes(pct, brand)) +
  geom_col() +
  scale_x_continuous(labels = scales::percent) +
  scale_y_reordered() +
  facet_wrap(~category, scales = "free_y") +
  labs(x = '% of Commericials each Brand uses these ad variables in',
       title = 'How do different Brands advertise in Super Bowl Commercials?')
ggsave('sb_plot8.png', width = 8, height = 5)

# plot 9 heatmap
by_brand %>%
  ggplot(aes(category, brand, fill = pct)) +
  geom_tile() +
  scale_fill_gradient2(low = 'blue', high = 'red', midpoint = .5) +
  labs(x = 'Category',
       y = NULL,
       title = 'Heat Map of Ad Characteristics Used in Super Bowl Commericals ',
       fill = '% Used')
ggsave('sb_plot9.png', width = 8, height = 5)
