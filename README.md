# Assignment_3_Resubmission
Course: Collecting Data | Student Number: S6494935

### 1. Different Website Scraped for Resubmission
The webpage that I had scraped and handed in for [Assignment 3](https://github.com/Cameron-Meinsma/Assignment_3.git) was the [U.S. topic on Google News](https://news.google.com/topics/CAAqIggKIhxDQkFTRHdvSkwyMHZNRGxqTjNjd0VnSmxiaWdBUAE?hl=en-US&gl=US&ceid=US%3Aen). However, I have decided to switch from the U.S. topic on Google News to the [Dutch Outdoor Women's Field Hockey National Team webpage](https://www.fih.hockey/outdoor-rankings/netherlands-women-hockey-rankings-48) on the [International Hockey Federation (FIH) website](https://www.fih.hockey/). The reason for this is that I believe that the FIH website highlights my skills more, due to the structure of the website being completely different from the Selenium scraping notebook. To elaborate, the notebook consists of the scraping of the [Ground News website](https://ground.news/), which is a news website. Therefore, during the original submission I was able to simply follow the steps in the notebook for the most part, without having to figure out too much on my own. The Dutch women's field hockey team webpage however, consists of a dynamic table where one can select a specific year from a dropdown menu, which changes the values in the table, and where one can click on a row to expand it and see more information.

### 2. Corpus
The corpus consists of 1 CSV file, which contains 10 columns:
| Column Name | Description |
| :--- | :--- |
| date | The date of the match. |
| competition_type | The type of competition.  |
| competition | The name of the competition. |
| netherlands_score | The amount of goals scored by The Dutch women's team during a specific match. |
| opponent_score | The amount of goals scored by the opponent during the same match. |
| opponent | The country of the opponent. |
| result | If the Dutch women's team had won or lost. In case there were shootouts, it will state that as well. |
| points_before_match | The amount of points that the Dutch women's team was worth before the match. |
| points_after_match | The amount of points that the Dutch women's team is worth after the match, based on the following formula: P(after) = P(before) + Result × Weighting × Importance*. |
| points_difference | The amount of points that were exchanged, based on the following formula: P(difference) = Result × Importance × Weight*. |

*For more information, see: https://www.fih.hockey/static-assets/pdf/fih-world-ranking-system-january-2020.pdf

### 3. Scraped Data
The data consists of a dynamic table of every match played by the Dutch Outdoor Women's Field Hockey National team, between 2020 and the present. This table is available on the FIH website, and can be found under Rankings.

The total amount of matches scraped conists of 118 matches, and they were all scraped on the 20th of December, 2025. The oldest match in the table was played on the 11th of January 2020 against China, which resulted in a 3 - 0 win for The Netherlands, and the latest match was on the 12th of December 2025 against Germany, which resulted in a 5 - 1 win for The Netherlands.

### 4. Cleaning of the Data
I removed the (5) or (10) in the `result` column, because they are part of a formula to calculate the amount of points that are exchanged after a match. Moreover, those numbers between parentheses are not necessary to know the result of the match. The amount of points that are exchanged after a match can also be found in the *nl_women_fih.csv* file, as part of the `point_difference` column.

### 5. Format of the Files in the Corpus
The corpus is in CSV format.

### 6. Robots.txt file
The robots.txt file contains the following:
```
User-agent: *
Disallow: /scrapperlayout
Disallow: */page/*?loadmore=*
Disallow: /data-api
```
Based on that, I inferred that it is legal for me to scrape the table of the Dutch women's outdoor field hockey national team, considering the url to that page is as follows: https://www.fih.hockey/outdoor-rankings/netherlands-women-hockey-rankings-48