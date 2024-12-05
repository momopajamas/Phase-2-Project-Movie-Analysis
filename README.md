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

#### Limitations
**We did not look at closer data such as budget, director, cast.**
Though these factors could be useful in determining which directors are more likely to create a successful movie, which actors are more likely to draw audiences, and how much of a budget could be expected to produce a hit movie, in reality these factors are more difficult to account for and too unreliable (for example, it's not a guarantee that a certain budget can be acquired, or that desired directors or actors could be secured).

Since these factors lie largely outside the realm of our control, it's better to look at which types of movies perform well before considering details such as cast and director.

**We did not factor in longevity or demand on streaming.**
Unfortunately, streaming services tend to be generally tight-lipped about the performance of the products on their platforms. However, we can reasonably assume that movies that perform well at the box office and also garner a wide audience would be sought after by streaming platforms.

**We did not look at role of discourse, social media buzz, word of mouth, etc.**
As these matters are largely outside the realm of our inquiry, and more difficult to ascertain to a definitive degree as opposed to hard numbers such as gross and critical reception, we were unable to factor these into our assessment, though we can also reasonably assume that movies that perform well and are widely viewed would correlate to higher degrees of online discourse and social media buzz.

Despite these limitations, we have been able to identify **which genres tend to perform the best at the box office, attract the widest audience, and are best received on average by audiences and critics,** which will be outlined in our recommendations below.

## Data Visualizations & Results
After cleaning the data to exclude outliers, we are able to gain the following insights. We will be brief here and share the most important insights, but for a more thorough breakdown of the visualizations please see the [Jupyter Notebook](https://github.com/momopajamas/Phase-2-Project-Movie-Analysis/blob/main/Movie%20Analysis.ipynb).

![top10_bottom10_rating_vote](https://github.com/user-attachments/assets/4c2bc387-2257-4a45-9cee-a93f35485058)
Here's what we can tell from this:
- There is a wide margin of difference between average vote count of both Top 10 and Bottom 10 movies.
- While `Western` movies have the highest average vote count by far, their critical reception is not much different from other genres.
- `Sci-Fi` movies have high average vote count, but are not present in the Top 10 for average rating.
- `News` and `Documentary` movies have starkly lower average vote counts than any other genre in the Bottom 10.
- `Horror` movies have the lowest average rating in the Bottom 10 and are not present in the Top 10.

![average_gross_by_genre](https://github.com/user-attachments/assets/a7e0a01e-b00f-4daf-ad0c-600e6c05e237)
**The genres present in the poorest performing genres but absent from the highest performing:**

`Documentary`
`War`
`News`
`Crime`
`Romance`
`Mystery`
`Biography`
`Drama`

**Genres that are present in highest performing genres of both Top 25% and Bottom 75%:**

`Animation`
`Adventure`
`Sci-Fi`
`Musical`
`Family`
`Action`
`Fantasy`
`Comedy`
`Thriller`


The analysis we conducted gave us three different lists:

1. Highest Grossing Genres
2. Genres with the Highest Ratings
3. Genres with the Highest Vote Counts

Since we want to see which films perform the best across these categories, let's see which genres overlap across all three:
<img width="563" alt="highest_gross_vote_rating_table" src="https://github.com/user-attachments/assets/e797d090-fc2a-4f15-84c9-6e06d7815684">

It is interesting to note that `Animation` is the only genre that overlaps across all three of those list of metrics, indicating it is the only genre that is among the highest grossing, highets rated, and has the highest vote count.

## Recommendations
Based on the insights gained from the analysis above, where we looked at which genres of movies had the highest vote counts on IMDB, the highest ratings, and the highest gross, as well as which genres generally had poor records in those three categories, we're able to confidently provide three recommendations. Despite the limitations outlined, these recommendations are strong starting points to consider before moving into the details around budget, cast, director, etc.

1. We can confidently recommend investing in Animation as a genre that is most likely to draw large audiences, perform well in theaters, and be well-received by audiences and critics.

2. We recommend investing in some combination of 2-3 of the following genres, or combining 1-2 of the following genres with Animation:
  - `Adventure`
  - `Sci-Fi`
  - `Musical`
  - `Family`
  - `Action`
  - `Fantasy`
  - `Comedy`
  - `Thriller`
3. We recommend avoiding investment in the following genres which the analysis showed to be more risky:
  - `Documentary`
  - `War`
  - `News`
  - `Crime`
  - `Romance`
  - `Biography`
  - `Horror`
