# podexplore
Podcast recommendations using Latent Semantic Analysis/Indexing (LSA/LSI) of podcast descriptions.  

The results of this code are used on [podexplore.com](http://www.podexplore.com) to suggest similar podcasts.

There are two R markdown files here.  One is **podcast_data_scraper** and one is **podcast_data_modeler**.

**podcast_data_scraper** contains code that requests podcast info from the iTunes Search API and then uses the RSS URL to scrape description and keywords data.

**podcast_data_modeler** contains code that cleans up the description data; creates a document-feature matrix (DFM) using the podcast descriptions, keywords, and genre tags; applies TF-IDF weights to the DFM; uses the resulting matrix to create a reduced-dimension Latent Semantic Analysis (LSA) matrix; then finds pair-wise cosine similarities between each podcast description. The top (i.e., most similar) results for each podcast are printed as a JSON file which is used on podexplore.com to give results to queries. 
