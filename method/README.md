# METHOD

The following page shows the method and the workflow of the research on the prediciton problem. Namely, it includes the research questions and their significance, the hypothesis, and operational measures.

## Data Cleaning and preprocessing 

The initial Kaggle dataset was divided into separate CSV files for various news stations and time periods. These files were concatenated into a single dataframe to simplify analysis. Rows related to BBC News were excluded as they were irrelevant to the study specified in US news. Column names were standardized to lowercase for consistency, and new columns were added based on the “matchdatetime” column for better visualization and analysis. Through regular expressions, components related to time were extracted and placed into separate columns. Text within the “snippet” column underwent preprocessing by removing special characters, punctuation marks, and numbers. Additionally, the text was lemmatized using the spaCy library to reduce words to their base form.

## Summary Statistics and Visualization
Summary statistics and visualizations were generated to explore the distribution of data among different stations and over time. Frequency distributions of months were visualized using bar plots and time series analysis techniques. The time series depicted in *Figure 1* allows us to understand the distribution of the texts. For instance, when in late 2017 there is an increase in the number of texts in the dataset, observe that CNN is mostly responsible for that sharp increase. The second graph provides a brief overview of most common words in the document and their count for each station. This is significant to the study as it dives into the weights of the words in each document per station as opposed to a simple raw count of words. 

<img src="distribution_stations_common_words copy.png" alt="Flowchart" width="600"/>

<img src="FrequencyDistributionMonths copy.png" alt="Flowchart" width="600"/>

<img src="Summary_CountperStation copy.png" alt="Flowchart" width="600"/>

<img src="TimeSeriesAnalysis copy.png" alt="Flowchart" width="600"/>

<img src="wordcloud copy.png" alt="Flowchart" width="600"/>

## Fighting Words Analysis

The Fighting words analysis, introduced by Monroe et al. (2008), was implemented using Jack Hessel's GitHub repository (2020), which is based on Monroe et al.'s algorithm. Snippets corresponding to each station were extracted from the dataset and fed into the fighting words model. This computed z-scores for each word, indicating their significance between the stations. The resulting z-scores were tabulated to display the top words with the highest positive scores favoring CNN and the highest negative scores favoring Fox News.

To visually depict the fighting words analysis, bar plots and scatter plots were generated, following Monroe et al.'s approach. Bar plots, created using matplotlib and seaborn libraries, illustrate the top words favored by CNN and Fox News based on their z-scores. Scatter plots, adapted from Xanda Schofield's GitHub (2017), visualize the distribution of fighting words between the two stations. These plots graphically represent the significance of individual words in distinguishing between CNN and Fox News. Modifications were made to enhance clarity and interpretability, including adding axis labels, adjusting colors for distinction, reducing word label size, and saving the plot in png format. Furthermore, the analysis was extended to compute the other stations (in pairs) and bigrams, capturing not only individual words but also sequences of words (n-grams) with high z-scores. 
