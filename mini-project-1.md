Mini Data-Analysis Deliverable 1
================

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.3     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

3.  Make a repository in the <https://github.com/stat545ubc-2023>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/126199/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2023 Organization.

# Instructions

## For Both Milestones

- Each milestone has explicit tasks. Tasks that are more challenging
  will often be allocated more points.

- Each milestone will be also graded for reproducibility, cleanliness,
  and coherence of the overall Github submission.

- While the two milestones will be submitted as independent
  deliverables, the analysis itself is a continuum - think of it as two
  chapters to a story. Each chapter, or in this case, portion of your
  analysis, should be easily followed through by someone unfamiliar with
  the content.
  [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/)
  is a good resource for what constitutes “good code”. Learning good
  coding practices early in your career will save you hassle later on!

- The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

- Become familiar with your dataset of choosing
- Select 4 questions that you would like to answer with your data
- Generate a reproducible and clear report using R Markdown
- Become familiar with manipulating and summarizing your data in tibbles
  using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

- *apt_buildings*: Acquired courtesy of The City of Toronto’s Open Data
  Portal. It currently has 3455 rows and 37 columns.

- *building_permits*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 20680 rows and 14 columns.

- *cancer_sample*: Acquired courtesy of UCI Machine Learning Repository.
  It currently has 569 rows and 32 columns.

- *flow_sample*: Acquired courtesy of The Government of Canada’s
  Historical Hydrometric Database. It currently has 218 rows and 7
  columns.

- *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 10032 rows and 22 columns.

- *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
  rows and 21 columns.

- *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

- We hope that this project will serve as practice for carrying our your
  own *independent* data analysis. Remember to comment your code, be
  explicit about what you are doing, and write notes in this markdown
  document when you feel that context is required. As you advance in the
  project, prompts and hints to do this will be diminished - it’ll be up
  to you!

- Before choosing a dataset, you should always keep in mind **your
  goal**, or in other ways, *what you wish to achieve with this data*.
  This mini data-analysis project focuses on *data wrangling*,
  *tidying*, and *visualization*. In short, it’s a way for you to get
  your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr`
package, choose **4** that appeal to you based on their description.
Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

## **Data Sets**

1.  apt_buildings
2.  flow_sample
3.  vancouver_trees
4.  steam_games

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to
*explore* the datasets. Use your knowledge of dplyr to find out at least
*3* attributes about each of these datasets (an attribute is something
such as number of rows, variables, class type…). The goal here is to
have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

# Choosing a Dataset

**Steam Games**

``` r
glimpse(steam_games) #I used glimpse to examine the data. Steam games has 40,833 rows and 21 columns
```

    ## Rows: 40,833
    ## Columns: 21
    ## $ id                       <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14…
    ## $ url                      <chr> "https://store.steampowered.com/app/379720/DO…
    ## $ types                    <chr> "app", "app", "app", "app", "app", "bundle", …
    ## $ name                     <chr> "DOOM", "PLAYERUNKNOWN'S BATTLEGROUNDS", "BAT…
    ## $ desc_snippet             <chr> "Now includes all three premium DLC packs (Un…
    ## $ recent_reviews           <chr> "Very Positive,(554),- 89% of the 554 user re…
    ## $ all_reviews              <chr> "Very Positive,(42,550),- 92% of the 42,550 u…
    ## $ release_date             <chr> "May 12, 2016", "Dec 21, 2017", "Apr 24, 2018…
    ## $ developer                <chr> "id Software", "PUBG Corporation", "Harebrain…
    ## $ publisher                <chr> "Bethesda Softworks,Bethesda Softworks", "PUB…
    ## $ popular_tags             <chr> "FPS,Gore,Action,Demons,Shooter,First-Person,…
    ## $ game_details             <chr> "Single-player,Multi-player,Co-op,Steam Achie…
    ## $ languages                <chr> "English,French,Italian,German,Spanish - Spai…
    ## $ achievements             <dbl> 54, 37, 128, NA, NA, NA, 51, 55, 34, 43, 72, …
    ## $ genre                    <chr> "Action", "Action,Adventure,Massively Multipl…
    ## $ game_description         <chr> "About This Game Developed by id software, th…
    ## $ mature_content           <chr> NA, "Mature Content Description  The develope…
    ## $ minimum_requirements     <chr> "Minimum:,OS:,Windows 7/8.1/10 (64-bit versio…
    ## $ recommended_requirements <chr> "Recommended:,OS:,Windows 7/8.1/10 (64-bit ve…
    ## $ original_price           <dbl> 19.99, 29.99, 39.99, 44.99, 0.00, NA, 59.99, …
    ## $ discount_price           <dbl> 14.99, NA, NA, NA, NA, 35.18, 70.42, 17.58, N…

``` r
steam_games %>%
  group_by(types) %>%
  summarize((price=mean(original_price, na.rm=TRUE))) #I wanted to understand how the price of different types of games compared. The mean price of app is 53.2152, bundle  49.522251, and sub is 33.68975  
```

    ## # A tibble: 4 × 2
    ##   types  `(price = mean(original_price, na.rm = TRUE))`
    ##   <chr>                                           <dbl>
    ## 1 app                                              53.2
    ## 2 bundle                                           49.5
    ## 3 sub                                              33.7
    ## 4 <NA>                                             30.0

``` r
steam_games %>%
  group_by(types) %>%
  summarize((price_max=max(original_price, na.rm=TRUE))) #I was curious how expsensive each type of game could be.The maximum price of a an app is 730640, bundle is 528.99, and sub is 999
```

    ## # A tibble: 4 × 2
    ##   types  `(price_max = max(original_price, na.rm = TRUE))`
    ##   <chr>                                              <dbl>
    ## 1 app                                             730640  
    ## 2 bundle                                             529. 
    ## 3 sub                                                999  
    ## 4 <NA>                                                30.0

**Flow Sample**

``` r
glimpse(flow_sample) #Flow sample has 218 rows and 17 columns
```

    ## Rows: 218
    ## Columns: 7
    ## $ station_id   <chr> "05BB001", "05BB001", "05BB001", "05BB001", "05BB001", "0…
    ## $ year         <dbl> 1909, 1910, 1911, 1912, 1913, 1914, 1915, 1916, 1917, 191…
    ## $ extreme_type <chr> "maximum", "maximum", "maximum", "maximum", "maximum", "m…
    ## $ month        <dbl> 7, 6, 6, 8, 6, 6, 6, 6, 6, 6, 6, 7, 6, 6, 6, 7, 5, 7, 6, …
    ## $ day          <dbl> 7, 12, 14, 25, 11, 18, 27, 20, 17, 15, 22, 3, 9, 5, 14, 5…
    ## $ flow         <dbl> 314, 230, 264, 174, 232, 214, 236, 309, 174, 345, 185, 24…
    ## $ sym          <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…

``` r
flow_sample %>%
  group_by(extreme_type) %>%
 summarize ((flow_mean=mean(flow, na.rm=TRUE))) #The mean minimum annual flow is 6.274112   and the mean maximum is 212.073394  
```

    ## # A tibble: 2 × 2
    ##   extreme_type `(flow_mean = mean(flow, na.rm = TRUE))`
    ##   <chr>                                           <dbl>
    ## 1 maximum                                        212.  
    ## 2 minimum                                          6.27

``` r
flow_sample %>%
  group_by(extreme_type) %>%
 summarize((flow_max=max(flow, na.rm=TRUE))) #The highest max flow recorded was 466 and the highest min flow recorded was 8.44
```

    ## # A tibble: 2 × 2
    ##   extreme_type `(flow_max = max(flow, na.rm = TRUE))`
    ##   <chr>                                         <dbl>
    ## 1 maximum                                      466   
    ## 2 minimum                                        8.44

**Vancouver Trees**

``` r
glimpse(vancouver_trees) #Vancouver trees has 146,611 rows and 20 columns
```

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149…
    ## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7…
    ## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "…
    ## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C…
    ## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL…
    ## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE…
    ## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "…
    ## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "…
    ## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "…
    ## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7…
    ## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "…
    ## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD…
    ## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, …
    ## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00…
    ## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "…
    ## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19…
    ## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08…
    ## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4…

``` r
vancouver_trees %>%
   filter(diameter > 100) #Out of 146,611 trees Vancouver has 10 extremely large trees, with diameters over 100
```

    ## # A tibble: 10 × 20
    ##    tree_id civic_number std_street   genus_name     species_name cultivar_name
    ##      <dbl>        <dbl> <chr>        <chr>          <chr>        <chr>        
    ##  1  182674         1488 E 64TH AV    ULMUS          AMERICANA    BRANDON      
    ##  2  184211         4210 W 16TH AV    QUERCUS        PHELLOS      <NA>         
    ##  3   23759          554 W 22ND AV    PRUNUS         SERRULATA    KWANZAN      
    ##  4   51001          849 W 60TH AV    ACER           SACCHARINUM  <NA>         
    ##  5   84751         8250 HUDSON ST    ACER           PLATANOIDES  <NA>         
    ##  6  199599         1194 ROSSLAND ST  STYRAX         JAPONICA     <NA>         
    ##  7  117345         7615 VIVIAN DRIVE CERCIDIPHYLLUM JAPONICUM    <NA>         
    ##  8   54498         6611 ADERA ST     ACER           PLATANOIDES  SCHWEDLERI   
    ##  9   78588         1333 W GEORGIA ST ACER           RUBRUM       <NA>         
    ## 10  149285         1906 W 14TH AV    ACER           SPECIES      <NA>         
    ## # ℹ 14 more variables: common_name <chr>, assigned <chr>, root_barrier <chr>,
    ## #   plant_area <chr>, on_street_block <dbl>, on_street <chr>,
    ## #   neighbourhood_name <chr>, street_side_name <chr>, height_range_id <dbl>,
    ## #   diameter <dbl>, curb <chr>, date_planted <date>, longitude <dbl>,
    ## #   latitude <dbl>

``` r
vancouver_trees %>%
 summarize((diameter_max=max(diameter, na.rm=TRUE))) #The largest diameter is an enormous 435
```

    ## # A tibble: 1 × 1
    ##   `(diameter_max = max(diameter, na.rm = TRUE))`
    ##                                            <dbl>
    ## 1                                            435

``` r
vancouver_trees %>% count(species_name) #I wanted to know the total number of species of trees present in Vancouver. I used count to determine all the unique variables within the column species_name and found that there are 283 species.
```

    ## # A tibble: 283 × 2
    ##    species_name       n
    ##    <chr>          <int>
    ##  1 ABIES            139
    ##  2 ACERIFOLIA   X  1724
    ##  3 ACUMINATA          7
    ##  4 ACUTISSIMA       526
    ##  5 AILANTHIFOLIA      5
    ##  6 ALBA              26
    ##  7 ALBA-SINENSIS      3
    ##  8 ALNIFOLIA        274
    ##  9 ALPINUM            1
    ## 10 ALTISSIMA          4
    ## # ℹ 273 more rows

**Apartment Buildings**

``` r
glimpse(apt_buildings) #Apartment building has 3,455 rows and 37 columns.
```

    ## Rows: 3,455
    ## Columns: 37
    ## $ id                               <dbl> 10359, 10360, 10361, 10362, 10363, 10…
    ## $ air_conditioning                 <chr> "NONE", "NONE", "NONE", "NONE", "NONE…
    ## $ amenities                        <chr> "Outdoor rec facilities", "Outdoor po…
    ## $ balconies                        <chr> "YES", "YES", "YES", "YES", "NO", "NO…
    ## $ barrier_free_accessibilty_entr   <chr> "YES", "NO", "NO", "YES", "NO", "NO",…
    ## $ bike_parking                     <chr> "0 indoor parking spots and 10 outdoo…
    ## $ exterior_fire_escape             <chr> "NO", "NO", "NO", "YES", "NO", NA, "N…
    ## $ fire_alarm                       <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ garbage_chutes                   <chr> "YES", "YES", "NO", "NO", "NO", "NO",…
    ## $ heating_type                     <chr> "HOT WATER", "HOT WATER", "HOT WATER"…
    ## $ intercom                         <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ laundry_room                     <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ locker_or_storage_room           <chr> "NO", "YES", "YES", "YES", "NO", "YES…
    ## $ no_of_elevators                  <dbl> 3, 3, 0, 1, 0, 0, 0, 2, 4, 2, 0, 2, 2…
    ## $ parking_type                     <chr> "Underground Garage , Garage accessib…
    ## $ pets_allowed                     <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ prop_management_company_name     <chr> NA, "SCHICKEDANZ BROS. PROPERTIES", N…
    ## $ property_type                    <chr> "PRIVATE", "PRIVATE", "PRIVATE", "PRI…
    ## $ rsn                              <dbl> 4154812, 4154815, 4155295, 4155309, 4…
    ## $ separate_gas_meters              <chr> "NO", "NO", "NO", "NO", "NO", "NO", "…
    ## $ separate_hydro_meters            <chr> "YES", "YES", "YES", "YES", "YES", "Y…
    ## $ separate_water_meters            <chr> "NO", "NO", "NO", "NO", "NO", "NO", "…
    ## $ site_address                     <chr> "65  FOREST MANOR RD", "70  CLIPPER R…
    ## $ sprinkler_system                 <chr> "YES", "YES", "NO", "YES", "NO", "NO"…
    ## $ visitor_parking                  <chr> "PAID", "FREE", "UNAVAILABLE", "UNAVA…
    ## $ ward                             <chr> "17", "17", "03", "03", "02", "02", "…
    ## $ window_type                      <chr> "DOUBLE PANE", "DOUBLE PANE", "DOUBLE…
    ## $ year_built                       <dbl> 1967, 1970, 1927, 1959, 1943, 1952, 1…
    ## $ year_registered                  <dbl> 2017, 2017, 2017, 2017, 2017, NA, 201…
    ## $ no_of_storeys                    <dbl> 17, 14, 4, 5, 4, 4, 4, 7, 32, 4, 4, 7…
    ## $ emergency_power                  <chr> "NO", "YES", "NO", "NO", "NO", "NO", …
    ## $ `non-smoking_building`           <chr> "YES", "NO", "YES", "YES", "YES", "NO…
    ## $ no_of_units                      <dbl> 218, 206, 34, 42, 25, 34, 14, 105, 57…
    ## $ no_of_accessible_parking_spaces  <dbl> 8, 10, 20, 42, 12, 0, 5, 1, 1, 6, 12,…
    ## $ facilities_available             <chr> "Recycling bins", "Green Bin / Organi…
    ## $ cooling_room                     <chr> "NO", "NO", "NO", "NO", "NO", "NO", "…
    ## $ no_barrier_free_accessible_units <dbl> 2, 0, 0, 42, 0, NA, 14, 0, 0, 1, 25, …

``` r
apt_buildings %>%
group_by(property_type) %>%
 summarize((year=mean(year_built, na.rm=TRUE))) #The mean year each property type was built: 1958 private house, 1983 social housing, 1975 TCHC
```

    ## # A tibble: 3 × 2
    ##   property_type  `(year = mean(year_built, na.rm = TRUE))`
    ##   <chr>                                              <dbl>
    ## 1 PRIVATE                                            1959.
    ## 2 SOCIAL HOUSING                                     1983.
    ## 3 TCHC                                               1976.

``` r
apt_buildings %>% 
summarize((height=max(no_of_storeys, na.rm=TRUE))) #The tallest apartment is a 51-storey building
```

    ## # A tibble: 1 × 1
    ##   `(height = max(no_of_storeys, na.rm = TRUE))`
    ##                                           <dbl>
    ## 1                                            51

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you’ve explored the 4 datasets that you were
initially most interested in, let’s narrow it down to 1. What lead you
to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

I’ve decide to work with the flow_sample data set for several reasons. I
was drawn to it initially because I’m an ecologist and I’m typically
most interested in working with environmental data. I like that it has a
time component, because that help me think about a number of questions I
could ask involving change over time. I was interested in the fact that
there’s a minimum and maximum flow recorded each year, and I’m curious
what the relationship between the two will look like. I also like that
it’s smaller than some of the other data sets and I can more easily
check for mistakes.
<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the
beginning, it’s important to have an *end goal* in mind. For example, if
I had chosen the `titanic` dataset for my project, I might’ve wanted to
explore the relationship between survival and other variables. Try to
think of 1 research question that you would want to answer with your
dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

Using the flow_sample data I want to know whether the intensity and
variability of the minimum and maximum flows has changed over the
duration of the study to understand whether climate change might have an
effect on flow rates.
<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to
dive deeper into your data. All datasets are different and therefore,
not all of these tasks may make sense for your data - which is why you
should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.
2.  Create a new variable based on other variables in your data (only if
    it makes sense)
3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.
5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…
6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!
7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

# Exploring the Flow Dataset

**Scatterplot** I made a scatterplot with year as my explanatory
variable on the X-axis and flow as my response variable on the Y-axis. I
color coded the points to separate the minimum and maximum flows. I also
fitted a trend line to the minimum and maximum flows to examine change
over time. I also changed the labels and theme to improve the
aesthetics. Maximum flow appears to have declined slightly over time,
while minimum flow appears to remain fairly constant, although it would
be better to create a plot with just minimum flow data to look more
closely.

``` r
ggplot(flow_sample, aes(x=year, y=flow, color=extreme_type)) +
  geom_smooth(method=lm) +
  geom_point() +
  theme_minimal() +
  xlab("Year") +
  ylab("Flow")
```

    ## `geom_smooth()` using formula = 'y ~ x'

    ## Warning: Removed 2 rows containing non-finite values (`stat_smooth()`).

    ## Warning: Removed 2 rows containing missing values (`geom_point()`).

![](mini-project-1_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

**Histogram** I made a histogram showing the frequency distribution of
the flows. I color coded minimum and maximum flows to correspond with
the scatterplot for consistency. I also change the theme, labels, legend
title, and bin width. This histogram shows that their is far more total
variation among maximum flows than minimum flows. However, it only shows
absolute variation and not proportional variation, which might be a more
useful measurement given that mininimum flows are all much lower. It
also shows that the maximum flow distribution is right-skewed.

``` r
ggplot(flow_sample, aes(x=flow, fill=extreme_type)) + 
  geom_histogram(binwidth = 15) +
  theme_minimal() +
  xlab("Year") +
  ylab("Flow") +
  scale_fill_discrete(name = "Extreme type")
```

    ## Warning: Removed 2 rows containing non-finite values (`stat_bin()`).

![](mini-project-1_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

**Boxplot** I made a boxplot to compare the distribution of maximum
flows recorded in each month. I changed the theme and labels and faceted
it so that each month would be visible. From these plots we can see that
June (month 6) has the highest average maximum flow and widest range.
August appears to have a very small number of values.

``` r
flow_sample %>%
  filter(extreme_type == "maximum") %>%
  ggplot(aes(x=extreme_type, y=flow)) + 
  geom_boxplot() +
  theme_minimal() +
  xlab("Year") +
  ylab("Flow") +
  facet_wrap(~month)
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

**Filter** I filtered the data to look at four different categories. The
first two are maximum flows greater than 300 before and after 1963 which
was the halfway point in the date range. I was curious if the prevalence
of extremely high flows (which I define as over 300) appears to have
increased. I found that their were 5 extremely high flows before 1963
and 5 after. So I did not find a change. I then filtered for extremely
low flows (\<5) before and after 1963. I found 6 extremely low flows
before and only 2 after. I want to investigate the minimum flows more to
see if there is a pattern there.

``` r
flow_sample %>%
    filter(extreme_type == "maximum") %>%
    filter(flow>300) %>%
    filter(year>1963)
```

    ## # A tibble: 5 × 7
    ##   station_id  year extreme_type month   day  flow sym  
    ##   <chr>      <dbl> <chr>        <dbl> <dbl> <dbl> <chr>
    ## 1 05BB001     1972 maximum          6    12   311 <NA> 
    ## 2 05BB001     1974 maximum          6    25   317 <NA> 
    ## 3 05BB001     1986 maximum          6     2   313 <NA> 
    ## 4 05BB001     2012 maximum          6     7   332 <NA> 
    ## 5 05BB001     2013 maximum          6    21   466 <NA>

``` r
flow_sample %>%
    filter(extreme_type == "maximum") %>%
    filter(flow>300) %>%
    filter(year<1963)
```

    ## # A tibble: 5 × 7
    ##   station_id  year extreme_type month   day  flow sym  
    ##   <chr>      <dbl> <chr>        <dbl> <dbl> <dbl> <chr>
    ## 1 05BB001     1909 maximum          7     7   314 <NA> 
    ## 2 05BB001     1916 maximum          6    20   309 <NA> 
    ## 3 05BB001     1918 maximum          6    15   345 <NA> 
    ## 4 05BB001     1923 maximum          6    14   377 <NA> 
    ## 5 05BB001     1933 maximum          6    17   311 <NA>

``` r
flow_sample %>%
    filter(extreme_type == "minimum") %>%
    filter(flow<5) %>%
    filter(year>1963)
```

    ## # A tibble: 2 × 7
    ##   station_id  year extreme_type month   day  flow sym  
    ##   <chr>      <dbl> <chr>        <dbl> <dbl> <dbl> <chr>
    ## 1 05BB001     1980 minimum          3     4  4.14 B    
    ## 2 05BB001     1995 minimum          2    11  4.85 B

``` r
flow_sample %>%
    filter(extreme_type == "minimum") %>%
    filter(flow<5) %>%
    filter(year<1963)
```

    ## # A tibble: 6 × 7
    ##   station_id  year extreme_type month   day  flow sym  
    ##   <chr>      <dbl> <chr>        <dbl> <dbl> <dbl> <chr>
    ## 1 05BB001     1919 minimum          2    28  4.56 B    
    ## 2 05BB001     1929 minimum          4     8  4.9  B    
    ## 3 05BB001     1931 minimum          3    26  4.7  B    
    ## 4 05BB001     1932 minimum          1     5  3.62 B    
    ## 5 05BB001     1934 minimum          2    26  4.08 B    
    ## 6 05BB001     1951 minimum          3     5  4.25 B

<!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar
with it through exploring the data. You have also brainstormed one
research question that interested you (Task 1.4). Now it’s time to pick
4 research questions that you would like to explore in Milestone 2!
Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->

# Choosing a research question

I want to explore these 4 questions:

1.  Are intensity of minimum and maximum flows correlated each year? I’m
    curious if some years tend to be wet years and some are dry year or
    if instead minimum and maximum flows are decoupled.
2.  Are there significant differences between the maximum flows of each
    each decade? 1921-1930, 1931-1940, etc. What about the minimum
    flows?
3.  Have maximum or minimum flows changed over time?
4.  Are there significant differences between the intensity of maximum
    flows recorded in different months? What about minimum flows?
    <!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

- In a sentence or two, explains what this repository is, so that
  future-you or someone else stumbling on your repository can be
  oriented to the repository.
- In a sentence or two (or more??), briefly explains how to engage with
  the repository. You can assume the person reading knows the material
  from STAT 545A. Basically, if a visitor to your repository wants to
  explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

- All Rmd files have been `knit`ted to their output md files.
- All knitted md files are viewable without errors on Github. Examples
  of errors: Missing plots, “Sorry about that, but we can’t show files
  that are this big right now” messages, error messages from broken R
  code
- All of these output files are up-to-date – that is, they haven’t
  fallen behind after the source (Rmd) files have been updated.
- There should be no relic output files. For example, if you were
  knitting an Rmd to html, but then changed the output to be only a
  markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
