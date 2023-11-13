# NoSQL-Challenge
------------
## Project Description

### Goal
Learn how to use Pymongo and pprint to analyze and organize data relating to food hygiene in the UK. 

------------
## Credits
I used ChatGPT when I got stuck. The data used was from the UK Food Standards Agency. UK Food Standards AgencyLinks to an external site. (2022). UK food hygiene rating data API. https://ratings.food.gov.uk/open-data/en-GBLinks to an external site.. Contains public sector information licensed under the Open Government Licence v3.0Links to an external site.
Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8)..

------------
## Softwares Used
### Libraries
PyMongo
PPrint
Pandas

### Language
Python
SQL

### Software
VSCode
GitLens

------------
## Database and Jupyter Notebook Set Up
## Part 1: Mars News
- Imported the establishments.json file from MongoDB.
- Named the database and the collection.
- Imported required libraries.
- Confirmed that the database uk_food was created and that the data was loaded properly.
- Verified that the collection establishments existed in the uk_food database and assigned establishments as a variable for later use.

## Part 2: Updating the Database
- Updated the database with a new restaurant, Penang Flavours, with the information provided.
- Queried the BusinessType for Rastaurant/Cafe/Canteen to find the BusinessTypeID since the new entry did not contain the BusinessTypeID.
- Updated the Penang Flavours entry with the correct BusinessTypeID.
- Removed all of the establishments in the Dover Local Authority.
- Converted the latitude and longitude from string type to float type entries.
- Converted the RatingValue from string type to integer type.
    - This included setting all none numeric ratings to Null.

### Exploratory Analysis
- Answered the following questions:
  1. Which establishments have a hygiene score equal to 20? The answer is 41.
     This involved using count_documents with a query to find the establishments that meet the criteria, pretty printing the first result to verify that the query       executed correctly, and converting the results to a dataframe with Pandas.
  2. Which establishments in London have a RatingValue greater than or equal to 4? The answer is 33.
     This involved querying the establishments in london with a RatingValue of 4 or greater (using regex to find entries that included London), using     
     count_documents to find the number of documents, pretty printing the first result to verify the data was queried correctly, and converting the results to a   
     dataframe with Pandas.
  3. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score (which corresponds with the best hygiene), nearest the the new            restaurant, Penang Flavours? see image below
     ![image](https://github.com/SamanthaMcKay/NoSQL-Challenge/assets/132176159/30d5ad9e-2f9b-4d22-8c79-977e481e0857)
    This involved retrieving the latitude and longitude of Penang Flavours, calculating the minimum and maximum latitudes and longitudes, sorting by hygiene score       in ascending order, limiting the query to the first five, and converting the results to a dataframe.
  4. How many establishments in each Local Authority area have a hygiene score of 0, sorted from highest to lowest count with the top ten local authority areas           printed out? See below image

     ![image](https://github.com/SamanthaMcKay/NoSQL-Challenge/assets/132176159/e480da9a-3723-49e9-8140-b296b0ced81f)

     ![image](https://github.com/SamanthaMcKay/NoSQL-Challenge/assets/132176159/3423a6d9-16dd-4ded-9602-da3151503ffb)

     This involved using an aggregation pipeline to find establishments with a hygiene score of 0, group by the LocalAuthorityName, count the number of entries for     each local authority, sort highest to lowest for the number of establishments in each local authority, pretty printing the first 10 results, and converting the     results to a dataframe.

## Conclusion
I learned much about Pymongo and PrettyPrint. I struggled with the aggregation pipeline in particular. I enjoyed diving deeper into noSQL databases and getting a refresher on SQL querying and the different flavours that SQL comes in. PyMongo is a powerful tool for querying. 
