# So, You Want to Get Into Movies?

Flatiron School Data Science: Phase 2 Project
- **Student**: Mohammad Abou-Ghazala
- **Instructor**: Mark Barbour

![image](https://github.com/user-attachments/assets/51e5f0d9-f3f3-45d5-a1b7-8d2b758ecbb4)

Image Source: [Freepik](https://www.freepik.com/free-photo/assortment-cinema-elements-red-background-with-copy-space_7089700.htm#fromView=keyword&page=2&position=1&uuid=2a77a8e2-14da-45ff-87ae-2c66125c9092)

## Overview
This project analyzes data from a number of sources regarding the reception, reach, and box office performance of movies. We mainly looked at data from **IMDB** and **Box Office Mojo**, which contain information regarding tens of thousands of movies.

In looking at this data, we are able to provide our company, which wants to enter the movie-production business, with a number of recommendations as to where to get started and which genres are good investments, namely:
1. That `Animation` is the best genre to invest in
2. Which secondary genres are likely good investments
3. Which genres to avoid due to risk

## Business Understanding
As the COVID-19 pandemic has more or less subsided, it left an indelible mark on the movie theater world, particularly with regards to the role of streaming platforms. A movie's success can no longer just be measured in terms of profits generated at the box office, as movies often are released straight to streaming platforms or in conjunction with a theatrical release, in addition to the fact that movies will often receive a "second life" upon its release on streaming. In other words, it is not sufficient only to consider movies' financial performance at the box office, and we need to consider other metrics in conjunction.

Furthermore, while it may be tempting to consider the relaionship of factors such as cast composition, the director, and budget breakdown to a movies' success, these factors tend to be out of our control for a variety of reasons. Instead, by focusing on genres more broadly, we are able to consider factors that are entirely within our control and learn which decisions would most likely lead to the best results. 

With this context in mind, we attempt to answer the following questions:
1. Which types of movies tend to perform best in terms of gross?
2. Which movies are well-received by audiences and critics, thus more likely to be in demand by streaming platforms?

## Data Understanding & Preparation
`IMDB` is considered an essential source for data on movies, their reception, and performance, as it contains basic information on a movie's production as well as crowd-sourced user reviews. 

From this dataset there are three factors of particular interest to us:
1. `Genres` which can tell us which tupes of movies are generally well-received
2. `Average Rating` which tells us which movies were generally well-received by the public and critics
3. `Number of Votes` which indivates how many individuals gave ratings for a movie, positive or negative

The issue to keep in mind is that it contains data for all sorts of movies, including lesser known titles that may have had a negligible performance at the box office but still garnered a niche cult-following. In essence, these factors will help us to determine which types of films are more likely to reach a wider audience (represented by `Number of Votes`) and which are best received critically (represented by `Average Rating`), both of which can shape a movie's demand among streaming platforms following theatrical release.

Also worthy of note is that the vast majority of films include a wide variety of genre combinations, with an estimated count of unique combinations in the tens of thousands. Of course it will be much more difficult to analyze genres based on these combinations, and instead we need to consider which genres appear the most within those combinations.

The other dataset we use is from `Box Office Mojo` which contains data on a movie's domestic and foreign gross. This dataset is more limited, containing information for just a few thousand compared to `IMDB`'s tends of thousands. Nontheless, we can use this dataset to reinforce our analysis as to which movies perform best in theaters if we combine the two datasets based on which movies appear in both.

In sum, we will investigate the relationship between `Genre` and `Average Rating`, `Average Total Gross`, and `Average Vote Count` to get a well-rounded picture of which genres of movies are the safest to invest in.

## Data Visualizations & Results
After cleaning the data to exclude outliers, we are able to gain the following insights:
