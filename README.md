# data-512-homework_2
This repository contains all of the necessary files and code that were used and generated by HW2: Homework 2—Considering Bias in Data in the DATA 512 Course as part of the UW MSDS Program. 

## Goal
The primary objective of this project is to analyze Wikipedia article coverage and quality across various countries and regions. By merging multiple datasets, including population statistics and article quality predictions, we aim to calculate key metrics such as total articles per capita and high-quality articles per capita. This analysis provides insights into the accessibility and representation of information across different geographic areas, highlighting potential biases and gaps in Wikipedia's content.

##  Data Sources

The data was acquired from two sources. First, from the Wikimedia Analytics API's Pageviews API, which provides access to traffic data for articles across the English Wikipedia. For more information on the API, please see the Wikimedia Pageviews API documentation.

Second, the predicted quality scores for each article in the Wikipedia dataset were obtained using a machine learning system called ORES (Objective Revision Evaluation Service). ORES is a machine learning tool that estimates Wikipedia article quality. The article quality estimates are, from best to worst:
- FA : Featured article
- GA : Good article (also known as A-Class)
- B : B-Class article
- C : C-Class article
- Start : Start-class article
- Stub : Stub-class article

You can use the API: Info request to get a range of metadata on an article, including the most current revision ID of the article page.

Two raw data files were used in this analysis: 

- `politicians_by_country_AUG.2024.csv`: The data in this file was obtained by web crawling the Wikipedia pages to generate a list of Wikipedia article pages about politicians from a wide range of countries. 

- `population_by_country_AUG.2024.csv`:This dataset was downloaded from the world population data sheet published by the Population Reference Bureau.

## License
This code example was developed by Trisha Prasant for use in DATA 512, a course in the UW MS Data Science degree program. The code is available under the MIT License. See the LICENSE file for more details.

The dataset used in this project is derived from the Wikimedia API, which is subject to the Wikimedia Foundation Terms of Use. The data retrieved through the API is available for reuse under the terms of use of this license, provided attribution is given.

## Intermediate and Final Data Files Description:

### Intermediate Data Files
- `ores_quality_scores.csv`: Dataset with Page Quality Scores from the ORES Model, the article title, and the Revision ID from the Wikimedia Page Info API.

### Final Data Files
- `wp_politicians_by_country.csv`: Wikipedia politician article data with columns for the country, region, population article_title,revision_id, and article_quality of each article about a given politician in the provided dataset.
- `wp_countries-no_match.txt`: Text file of all countries for which there are no matches, with each country on a separate line.

##  Final Dataset Schema
The final data file `wp_politicians_by_country.csv` contains the following fields:

| Column Name     | Type   | Description                                                                                                                                     |
|-----------------|--------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| country         | string | The name of the country or region that the article's POI (person of interest) is from.                                                          |
| region          | string | The geographic region assigned to the country, reflecting its hierarchical position in a regional structure.                                    |
| population      | float  | The population of the country, represented in millions.                                                                                         |
| article_title   | string | The title of the Wikipedia article associated with the country or region.                                                                       |
| revision_id     | float  | The unique identifier for the specific revision of the Wikipedia article.                                                                       |
| article_quality | string | The predicted quality of the Wikipedia article, classified as "FA" (Featured Article), "GA" (Good Article), or other categories (e.g., "Stub"). |

## Known Issues and Special Considerations
- **Data Gaps**: Some countries or regions may lack corresponding entries in the population dataset or Wikipedia articles. This can lead to misleading metrics if not carefully accounted for during analysis. Specifically, there are no articles present in the data set that are found in North America. To find a list of of countries that there is no data for, please refer to this file: `wp_countries-no_match.txt`. 
Bias in Article Representation**: The data may reflect systemic biases in Wikipedia's content creation, which is often influenced by editor demographics and resource availability, leading to disparities in article coverage and quality.
- **Hierarchical Regions**: Countries were assigned to regions based on a hierarchical structure. Some countries may fit into multiple regions; however, for this analysis, they were placed in the closest (lowest in the hierarchy) region.
- **Infinite Values**: Some countries and regions showed infinite values for articles per capita, which indicates either very low population counts or a high number of articles relative to population size. Further investigation is needed to interpret these cases appropriately.

## Research Implications

Throughout this homework assignment analysis, I learned that the distribution of Wikipedia articles does not reflect population size or political importance; it represents deeper societal biases. For example, I was surprised to find that countries with significantly smaller populations, such as Tuvalu and Monaco, had a disproportionately high number of articles, resulting in infinite ratios per capita. This discrepancy suggests that these countries might have a dedicated base of contributors who prioritize documenting their own history and culture. On the other hand, I also noticed that highly populated countries like China and India ranked at the bottom for total articles per capita, which made me think of questions about the factors that might contribute to this disparity. 

These findings show biases stemming from varying levels of internet accessibility, the presence of active Wikipedia editors, and cultural priorities around information sharing. Overall, this analysis reinforced the idea that while Wikipedia aims to be a global knowledge repository, the actual representation of countries is uneven and influenced by complex socio-political dynamics.

#### What biases did you expect to find in the data (before you started working with it), and why?
Before starting the analysis, I expected to find biases related to the representation of countries on Wikipedia. I thought countries with larger populations or more prominent global influence, such as the United States and China, would have significantly more articles than smaller nations. I also suspected that certain regions, particularly those with limited internet access or lower levels of digital literacy, might be underrepresented in terms of article coverage and quality. This expectation stemmed from the understanding that Wikipedia is a user-generated platform, where content creation is often influenced by contributors' geographic, cultural, and economic backgrounds.

#### What might your results suggest about the internet and global society in general?
The analysis results reveal important insights about how knowledge is distributed across the globe. There is a stark contrast in article coverage and quality between various countries, indicating that the internet, while a powerful tool for democratizing information, also reflects existing inequalities. Countries with robust internet infrastructure (represented by European countries) and active online communities tend to have a more substantial presence on platforms like Wikipedia. At the same time, those facing challenges such as limited access or lower engagement levels need to be included. This disparity highlights the need to promote equitable knowledge sharing and representation in the digital world, suggesting that the internet is both an avenue for empowerment in social classes and also a method for exclusion.

#### How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?
<<<<<<< HEAD
To address the limitations and biases observed in the dataset, researchers could supplement the existing data with additional sources, such as demographic and socio-economic information from international databases like the World Bank or UN datasets. This could help orient these findings and provide a more varied understanding of things that might influence article creation and quality. Additionally, researchers could incorporate qualitative data, such as surveys or interviews with Wikipedia editors from diverse backgrounds, to gain insights into their motivations and experiences. 





=======
To address the limitations and biases observed in the dataset, researchers could supplement the existing data with additional sources, such as demographic and socio-economic information from international databases like the World Bank or UN datasets. This could help orient these findings and provide a more varied understanding of things that might influence article creation and quality. Additionally, researchers could incorporate qualitative data, such as surveys or interviews with Wikipedia editors from diverse backgrounds, to gain insights into their motivations and experiences. 
>>>>>>> a619a83 (updated README and notebook with comments.)
