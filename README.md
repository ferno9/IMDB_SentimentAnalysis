# IMDB_SentimentAnalysis

**Live Demo :**

https://huggingface.co/spaces/1nferno/Imdb_sentiment

## Explanation

A sentiment analysis on the IMDB Review dataset using the Universal Language Model Fine-tuning (ULMFit) a transfer learning approach on the AWD_LSTM Architecture.

The main idea of ULMFit is to take a pretrained model on a large text corpus like Wiki Text and then train it on the desired text dataset and reach same or even better accuracy in significantly less epocs than a model trained from scratch on the desired dataset only.

## Main ideas 

**Tokenizer :** Fastai tokenizer is used which has additional special tokes on top of spaCy

**TextBlock :** TextBlock provided by fastai automatically does the tokenization and numericalization of text. Along with setting the batch size and the sequence length.

**Architecture :** AWD_LSTM

**Learner :** The language model learner uses the pretrained weights of AWD_LSTM architecture trained on Wiki text 103.

**Training (intially text prediction) -** The model pretrained layers are freezed initially and only the new embeddings are trained by making the model predict the next words in the IMDB Reviews followed by unfreezed training for few epocs. After the model gains a understanding of the type of language used in the reviews which is different that Wiki text, the encoder is saved and a new head is made for the classifier followed by some epocs.

**Final Accuracy of Sentiment Classifier :- 94.7 %**


## Tools Used

Pytorch, Fastai, Numpy, Pandas
