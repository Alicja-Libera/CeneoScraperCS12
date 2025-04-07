# CeneoScraperCS12

# https://www.ceneo.pl/131301089?tag=producenci-electrolux

# Algoritm for extracting opinions about single product from Ceneo.pl 
1. Send the request for accesing first webpage with opinions about the product 
2. If response is okay, then we need to parse HTML page content into DON structure
3. Extract from DOM structure opinions and their components 
4. Assign opinions with their components to complex data structure
5. Is there are more pages with opinions, repeat steps 1-5 
6. Save data instructions with opinions into database 

# Structure of single opinons in Ceneo.pl

Compponent | Variable | Selector 
|--------|----------|--------| 
|opinion|opinion|
|opinion ID|opinion_id|["data-entry-id"]|
|opinion’s author|author|span.user-post__author-name|
|author’s recommendation|recommend|span.user-post___author-recomendation>em|
|score expressed in number of stars|stars|span.user-post__score-count|
|opinion’s content|content|div.user-post_text|
|list of product advantages|pros|div.review-feature__item--positive|
|list of product disadvantages|cons|div.review-feature__item--negative|
|how many users think that opinion was helpful||["data-total-vote"]|
|how many users think that opinion was unhelpful|down_votes|button.vote-no["data-total-vote"]|
|publishing date|published|span.user-post__published > time:nth-child(1)["datetime"]|
|purchase date|purchased|span.user-post__published > time:nth-child(2)["datetime"]