# Movies-ETL
Module 8 ETL work


## Summary

I have been working with Britta at Amazing Prime to prepare a Postgres database of movie data for a Hackathon. We needed to extract our data from both Wikipedia and MovieLens Kaggle data, transform (clean & merge) the raw data using Jupyter Notebook and Pandas, and then load the data into a Postgres database for the final product. For our final product, Amazing Prime asked us to prepare an automated workflow of our process, which involved refactoring our entire ETL code into a single function that would perform our process in the future with only a single tweak to the files' directory location (which is stored as a variable outside of the function itself). 


As an aside, my movies table in Postgres is one record less than what the Challenge expected me to have. I believe this discrepancy is due to me including the following code in my merged dataframe: 

    movies_df = movies_df.drop(movies_df[(movies_df['release_date_wiki'] > '1996-01-01') 
                                     & (movies_df['release_date_kaggle'] < '1965-01-01')].index)

which dropped that strange row of data where two films (one from 1996 and one from 1964) ended up sharing the same IMDB ID in the Wikipedia dataset and in the Kaggle dataset. I don't believe the Challenge specifically called to remove this row, but I included the code for the sake of having the cleanest data possible. Thank you!! 
