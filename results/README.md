# RESULTS
This section shows how the research answers each research question based on the specific methods.

## CNN vs. Fox News

The analysis begins by assessing features in CNN and Fox News snippets. Table 1 displays z-score values for the most significant features per station. Figure 2.1 offers an overall visualization of feature distribution, plotting weighted log-odds ratios (z-score) against word frequency. Blue denotes highest weighted words for CNN, red for Fox News. Gray points represent words with z-scores within the specified significance range by the “sig_val” parameter, indicating words not statistically significant in differentiating between CNN and Fox News texts.

<img src="CNN_Fox_table copy.png" alt="Flowchart" width="600"/>

<img src="fw_CnnFox_distribution_plot copy.png" alt="Flowchart" width="600"/>

*Figure 2.1: Feature evaluation and selection based on z-score. CNN texts are in blue while Fox News texts are in red. Those in gray are below the sig_val of 2.573.*

Figure 2.2 shows the top 10 CNN and Fox News words. 
<img src="top_wrds_cnn_fox copy.png" alt="Flowchart" width="600"/>

*Figure 2.2: The top 10 CNN and Fox News words are labeled and listed in rank order.*

CNN focuses on political aspects, urgency, and environmental impacts, evident in terms like "hoax," "Trump," and "crisis." In contrast, Fox News's coverage may emphasize skepticism, opposition to certain narratives, and broader political implications of environmental policies and initiatives. For instance, "sean" likely refers to Sean Hannity, a conservative commentator on Fox News known for his skepticism toward climate change science (Fox News Staff, 2022). 

Figure 2.3 shows the plot distribution of the z-scores and the highest 10 words for each station using bigrams. 

<img src="bigram_CnnFox_distribution_plot copy.png" alt="Flowchart" width="600"/>

<img src="top_bigrams_cnn_fox copy.png" alt="Flowchart" width="600"/>

*Figure 2.3 Feature evaluation and selection based on z-score with bigrams. CNN texts are in blue while Fox News texts are in red. The top 10 CNN and Fox News words are labeled and listed in rank order.*

In the bigram analysis, CNN's "climate crisis" contrasts with Fox News' "global warming." "Climate crisis" underscores urgency and severity, aligning with CNN's portrayal of climate change as pressing. In contrast, "global warming" may emphasize the scientific aspect, potentially downplaying urgency. This discrepancy reflects how networks prioritize and communicate environmental concerns. Fox News' frequent use of "not" or "do not" suggests a tendency to challenge certain narratives on environmental issues.

## CNN vs. Fox News

The process was repeated with CNN and MSNBC transcripts. Table 2 displays z-scores for the top five features per station, while Figure 3.1 visualizes their distribution with a bar chart of the top ten features.

<img src="MSNBC_CNN_table copy.png" alt="Flowchart" width="600"/>

<img src="fw_CnnMsnbc_distribution_plot copy.png" alt="Flowchart" width="600"/>

<img src="top_wrds_cnn_msnbc copy.png" alt="Flowchart" width="600"/>

*Figure 3.1 Feature evaluation and selection based on z-score. CNN texts are in blue while MSNBC texts are in red. The top 10 CNN and MSNBC words are labeled and listed in rank order.*

The method was repeated with bigrams (see Figure 3.2).

<img src="bigram_MsnbcCnn_distribution_plot copy.png" alt="Flowchart" width="600"/>

<img src="top_bigrams_msnbc_cnn copy.png" alt="Flowchart" width="600"/>

*Figure 3.2 Feature evaluation and selection based on z-score with bigrams. CNN texts are in blue while MSNBC texts are in red. The top 10 CNN and MSNBC words are labeled and listed in rank order.*

CNN's top words and bigrams indicate a broad focus on presidential actions, and environmental topics like cars, trees, and roads, suggesting comprehensive environmental coverage. In contrast, MSNBC emphasizes political dynamics, with mentions of the Republican Party, legislation, and politicians like US Senator Mitt Romney, highlighting a focus on political aspects, policy debates, and legislative efforts related to environmental issues. The inclusion of phrases like "barely" and "somewhere" may suggest a critical or skeptical tone toward certain political actions or positions on environmental matters.

## Fox News vs. MSNBC

The same process for Fox News and MSNBC. Table 3 shows the z-scores for the top five features per station, and Figures 4.1 and 4.2 the distribution, with 4.1 showing unigrams and 4.2 showing bigrams. 

<img src="Fox_MSNBC_table copy.png" alt="Flowchart" width="600"/>

<img src="fw_MsnbcFox_distribution_plot copy.png" alt="Flowchart" width="600"/>

<img src="top_wrds_msnbc_fox copy.png" alt="Flowchart" width="600"/>

*Figure 4.1 Feature evaluation and selection based on z-score. Fox News texts are in blue while MSNBC texts are in red. The top 10 Fox News and MSNBC words are labeled and listed in rank order.*

The method was repeated with bigrams (see Figure 3.2).

<img src="bigram_MsnbcFox_distribution_plot copy.png" alt="Flowchart" width="600"/>

<img src="top_bigrams_msnbc_fox copy.png" alt="Flowchart" width="600"/>

*Figure 4.2 Feature evaluation and selection based on z-score with bigrams. Fox News texts are in blue while MSNBC texts are in red. The top 10 Fox News and MSNBC words are labeled and listed in rank order.*

Fox News emphasizes attributing blame and expressing opinions on environmental topics, using phrases like "they be" and "you be," adjusted from "they are" and "you are" during lemmatization. MSNBC's focus is on political dynamics, particularly Republicans, with words like "hoax" and "deny" indicating a critical perspective on environmental narratives. 

# Evaluation

## TF-IDF
Comparing TF-IDF and Fighting Words helps evaluate model performance and interpretability. TF-IDF, a traditional method for feature extraction, assesses word importance by considering frequency within a document and rarity across the corpus. In contrast, Fighting Words, by Monroe et al., identifies words significantly associated with one group versus another. By comparing both methods' outputs, we can capture linguistic nuances and distinctive features in environmental news coverage, as well as comparing the innovative method with a baseline that is traditionally used. Moreover, Matthew Denny in his paper “Revisiting Fightin’ Words: Feature Selection Using an Informed Dirichlet Model” (2016) provides an alternative approach to improve TF-IDF. He proposes the following measure:

![\text{tf}"-" \text{idf}_{(w,k)}^{(i)} = \text{average} \, \text{tf}_{(w,k)}^{(i)} \times \text{idf}_w](https://render.githubusercontent.com/render/math?math=%5Ctext%7Btf%7D%22-%22%20%5Ctext%7Bidf%7D_%7B%28w%2Ck%29%7D%5E%7B%28i%29%7D%20%3D%20%5Ctext%7Baverage%7D%20%5C%2C%20%5Ctext%7Btf%7D_%7B%28w%2Ck%29%7D%5E%7B%28i%29%7D%20%5Ctimes%20%5Ctext%7Bidf%7D_w)




