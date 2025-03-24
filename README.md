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
|opinion|opinion|<div.opinion>|
|opinion ID|opinion_id|<div.opinion_id>|
|opinion’s author|author|<div.author>|
|author’s recommendation|recommend|<div.recommend>|
|score expressed in number of stars|stars|<div.stars>|
|opinion’s content|content|<div.content>|
|list of product advantages|pros|<div.pros>|
|list of product disadvantages|cons|<div.cons>|
|how many users think that opinion was helpful|up_votes||
|how many users think that opinion was unhelpful|down_votes||
|publishing date|published||
|purchase date|purchased||