# Project Title

This is the Crypto clustering application for challenge 10! Always been a big fan of statistics.

The application begins by pulling in a CSV file with crypto market data and checking out the first few rows.
I then run a summary statistic describe function on the data, and also plot the data to see how it looks for the different time periods that are in the CSV file.  So far so good.

After the above is done the fun begins. I run a fit_transform function on the data to turn everything into a mean 0 and variance 1 scaled datapoint, and I turn it into a dataframe and put the crypto currency names as the index of the dataframe. This index column I call "coin_id".  Now with the data scaled, I initialize a list from 0 to 10, called k, and I create an empty list called inertia.
From there I run a for loop over all the values of k and I fit the KMeans model for all the possible values of k I created.
This gives me 10 inertia values which I pair together with the corresponding k value in a dictionary, and I graph the dictionary after turning it into a dataframe. By examining the graph I can see after which value of k the inertia has the least amount of change to it. This is the value of k that corresponds to the ideal value of k needed for the number of clusters for the KMean value model to run as ideally as possible.

Now I get to cluster the crypto data with everything I just did above!  I initialize an instance of the KMean model with 4 clusters based on what was done above.  I run a predict function on the scaled crypto data to group the data based on the built-in model.
After this is done I create a copy of the original scaled data and add a new column with these new predict values that I got for each crypto currency.  From there I run an hv scatterplot and the clustering can be seen. Very exciting so far!

Now is when I get deep into it! The next step is to optimize the clustering by invoking the PCA method.  I instantiate an instance of the PCA model and pick three components.  I run the fit_transform function on the scaled crypto data and then run explained_variance_ratio_ on the data to see how much the three components explain the changes in the data as a whole. Turns out the three components do a pretty good job and explain nearly 90% of the variation in the data!

After the above is complete I create a new dataframe with this data and label the columns PC1, PC2, and PC3. I append the original
"coin_id" column to the dataframe and make it the index.  From here I do a very similar thing as above: I create a list of values for the KMean model from 0 to 11, labelling the variable k_pca.  I initialize an empty list called inertia_pca. I run a for loop where I run a fit function on the PCA crypto data I created in the previous paragraph.  After that I throw the calculated inertia_pca numbers with the corresponding k_pca values into a dictionary. After that I put the values into a dataframe and run an hvplot on everything.  From here I am able to visualize the elbow curve now but with the PCA slightly altered numbers. I get the same value as above with k = 4, but I think the value of 4 is more definite in this case. In the first elbow curve it was possible that k = 5 would work as well.

The final part is now running the KMean value clustering model on the PCA data!  Just like before I instantiate an instance of the KMean model with four clusters. I run a fit function and a predict function on the crypto PCA data.  From there I append the new predicted values on the datafram I had created with the columns PC1, PC2, and PC3.  Finally, I plot the crypto PCA data using an hv scatterplot. Very exciting! You can clearly see how running the PCA algorithm has essentially put the data through a sort of rotation
matrix and now everything is rescaled as a result.

In doing the comparison, one can see using fewer features to run the KMean model only simplifes the clustering and makes how the data reacts to the two main principal components very clear.

## Story

In this Challenge, you’ll combine your financial Python programming skills with the new unsupervised learning skills that you acquired in this module.

You’ll create a Jupyter notebook that clusters cryptocurrencies by their performance in different time periods. You’ll then plot the results so that you can visually show the performance to the board.

The CSV file that’s provided for this Challenge contains the price change data of cryptocurrencies in different periods.

---

## Technologies

I am using python version 3.7.10 and am importing the following from the built-in libraries and from functions i've created myself:
import pandas as pd
import hvplot.pandas
from path import Path
from sklearn.cluster import KMeans
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler

---

## Installation Guide

I have python version 3.7.10 and git version 2.33.0.windows.2 installed on a laptop running windows 10 pro.

I launch jupyter lab from the gitbash terminal and then run the risk_return_analysis noteback from the 
webpage that launches.


---

## Usage

Just open the crypto_investments notebook and run the code. User can feel free to change any k values I used if they are curious what 
graphs will look like.

That's it!


---

## Contributors
Just me, Paul Lopez.


---

## License
No licenses required. Just install everything for free, pull from my repository, and enjoy!
