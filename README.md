# DATA_512_Assignment2
Assignment 2: Biases in Data for UW course HCDE 512

Created by: Libby Montague
Date: 10/29/2017

Goal: Identify biases in wikipedia articles are politicans from different countries. 

Source Data Information:
- Figshare: the wikipedia data on the politicans by country. 
    - Accessed on 10/29/2017.  
    - The data were released under the CC-BY-SA 4.0 license by Oliver Keyes. 
    - The data were downloaded from: https://figshare.com/articles/Untitled_Item/5513449. 
    - The script uses the 'page_data.csv' file stored in the working folder. The column headers should be: page, country, rev_id. This file includes the revision IDs for english Wikipedia articles about politicans and includes the nationality of the politician. The data are limited to politicians that are 2 levels into the heirarchy. 
- Population Research Bureau: the population data by country. 
    - Accessed on 10/20/2017. 
    - Copyrighted by the Population Reserach Bureau
    - The data was downloaded from: http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14. 
    - The script uses the 'Population Mid-2015.csv' file which was stored in the working directory. The column headers should be: Location, Location Type, TimeFrame, Data Type, Data, Footnotes. The only Location Type should be 'Country' and the only Data Type should be 'Number.'
- ORES API: use the API to acess the article quality for each fo the revision IDs in the Figshare data. 
    - Accessed on 10/29/2017. 
    - The data were accessed using this API: https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores
    - More information about the ORES project can be found here: https://www.mediawiki.org/wiki/ORES
    - The predicted score is the only value kept from the call. These results are then stored to a file in the working directory. The API call is slow, so this prevents the user from needing to call the API each time the script is run. 
- The processed and combined data are stored in wikipedia_ores_data_formatted.csv. 

Files:
- LICENSE 
  - The MIT License for the code (hcds-a2-bias.ipynb). 
- hcds-a2-bias.ipynb
  - Fully documentated jupyter python notebook that uses data from Figshare, Population Research Bureau, and ORES API to investigate bias of political articles per country. 
  - Includes a reflection on biases present in these data. 
  - Input: data tables from Population Research Bureau and Figshare. Additionally, the script accesses the ORES API. 
  - Output: processed and combined data from the three sources. A figure with four graphs showing the countries with the most and least political articles per capita and good quality political articles per capita. Good quality articles are defined as 'FA' or 'GA' scoring by ORES.
- wikipedia_ores_data_formatted.csv
  - The combined and processed data from the three sources. 
  - The table includes three columns: 
    - country - the country of the politician 
    - article_name - the name of the wikipedia page (article)
    - revision_id - the wikipedia revision id of the article
    - article_quality - quality of the article using the ORES classification (FA, GA, B, C, Start, Stub)
    - population - population of the country
- wikipedia_quality_by_country.png
    - The final visualization with 4 graphs. The 4 graphs include the countries with the with the most and least political articles per capita and good quality political articles per capita. 
    - Good quality articles are defined as 'FA' or 'GA' scoring by ORES.
