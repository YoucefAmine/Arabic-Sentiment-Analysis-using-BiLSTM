# Arabic Sentiment Analysis and Text Classification (Using BiLSTM)
Sentiment Analysis is to build machine learning models that can determine the tone (positive, negative, neutral) of the texts (e.g., movie reviews, tweets...). It is one of the most important and standard tasks in NLP. However, Arabic sentiment analysis has not been studied at a level as high as other languages (e.g., English, Chinese, French...). One of the key factors is the lack of high-quality and large-scale training data.

- ### Word Embedidng:
  - **[fastText](https://fasttext.cc/)** 
    - Arabic word vectors.
    - Dimension 150.
    
- ### Datasets:
  - **[ArSAS](https://homepages.inf.ed.ac.uk/wmagdy/resources.htm)**
    - Arabic Speech-Act and Sentiment Corpus of Tweets Dataset.
    - 21K Tweets.
    - 4 Classes: Negative, Positive, Mixed and Neutral.
  - **[LABR](https://github.com/mohamedadaly/LABR)**
    - Large-Scale Arabic Book Reviews Dataset.
    - 63K Book Reviews.
    - Rating: 1 to 5.
  - **[HARD](https://github.com/elnagara/HARD-Arabic-Dataset)**
    - Hotel Arabic Reviews Dataset.
    - 94K Hotel Reviews.
    - Rating: 1 to 5.

- ### Data Pre-processing:
  - Removal of Noise, URLs, Hashtag and User-mentions, Emoticons and Emojis.
  - Removing Punctuations.
  - Letter normalization.
  - Removing elongation and Arabic diacritics.
  - Removing Stopwords, stemming, and lemmatization steps were ignored.

- ### Hyper parameters:
| Parameter        | Value |
| ---------------- | ----- |
| Batch Size       | 128   |
| Learning Rate    | 0.01  |
| Optimizer        | adam  |
| Number of Epochs | 20    |

- ### Model:
The BiLSTM model is composed of an embedding layer, a BiLSTM layer with 64 LSTM cells, then the output is passed to a dropout layer with a 0.5 dropout rate then after that directly to the classification layer. The architecture used is shown in the figure below

![bilstmarchitecture](https://user-images.githubusercontent.com/45196964/214374190-c17632fb-dae8-4aa8-aa0b-72ce2dd2566f.png)

- ### Results:
| Datasets  | Precision | Recall | F1-Score | **Accuracy** |
| --------- | --------- | ------ | -------- | ------------ |
| **ArSAS** | 76%       | 67%    | 71%      | `71.74%`     |
| **LABR**  | 88%       | 89%    | 88%      | `88.92%`     |
| **HARD**  | 95%       | 95%    | 95%      | `94.82%`     |
