# Squad Question answering Project
# Question Answering in Squad 2.0
Natural language processing tasks such as machine reading comprehension and question-answering are crucial. Due to their outstanding performance in a variety of NLP tasks, Pre-trained Contextual Embeddings (PCE) models like Embeddings from Language Models (ELMo) and Bidirectional Encoder Representations from Transformers (BERT) have recently received a lot of attention. In this study, we adopted the various model and worked to improve its performance on the Stanford Question Answering Dataset (SQuAD 2.0). We carefully evaluated the performance of a number of output designs in comparison to all the models. 
## What is Question Answering?
There are different QA variants based on the inputs and outputs:
Extractive QA: The model extracts the answer from a context. The context here could be a provided text, a table or even HTML! This is usually solved with BERT-like models
Open Generative QA: The model generates free text directly based on the context
Closed Generative QA: In this case, no context is provided. The answer is completely generated by a model, as shown in the figure below

## Objective
2.1 Problem Formulation
We formulate the problem as follows → Given a question q and context c, identify spans within c that answer q. The schema below demonstrates this paradigm:

2.2 Dataset
We use the Stanford Question Answering Dataset (SQuAD) for pre-training, fine-tuning, and evaluating our models. SQuAD is a reading comprehension dataset, consisting of questions posed by crowdworkers on a set of Wikipedia articles, where the answer to every question is a segment of text, or span, from the corresponding reading passage.

We train pre-trained models based on the transformer architecture for this task, as explained in the next section. 

## Methodology
We train the following pre-trained models based on the transformer architecture for this task:
BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding (base-uncased variant)
BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding (base-cased variant)
RoBERTa: A Robustly Optimized BERT Pretraining Approach 
ELECTRA: Pre-training Text Encoders as Discriminators Rather Than Generators
DeBERTa: Decoding-enhanced BERT with Disentangled Attention
The transformer works as follows:
We implement these models in the following framework for extractive span-based question answering:
We implement the above models in Python using the following libraries: 
Huggingface Transformers
Happy Transformers
Huggingface Datasets

The RoBERTa model performs the best as measured by the F1 score, with a best F1 score of 92.74%  
However, RoBERTa is significantly slower than the other other models, with a throughput of just 49 samples per second as compared to ~60 samples per second by the other models
We observe that the DeBERTA model, in spite of performing comparably to RoBERTa, has significantly lower throughput

## Conclusion
In this project, we formulated the extractive question answering problem as: given a question q and context c, identify spans within c that answer q. We used the Stanford Question Answering Dataset (SQuAD), a reading comprehension dataset, consisting of questions posed by crowdworkers on a set of Wikipedia articles, for pre-training, fine-tuning, and evaluating our models.
Then, we applied the pre-trained models BERT, RoBERTa, ELECTRA, and DeBERTa, all based on the transformer architecture, for this task. We trained these models on a train split of the SQuAD dataset, keeping aside a separate set for validating the model performance on unseen data.
We calculated the F1 score, defined as the harmonic mean of the Precision and the Recall, for each model on the held out validation set, and observed that the RoBERTa model performs the best as measured by the F1 score, but the BERT model has the best latency and highest throughput. Hence, we conclude that the RoBERTa model is best suited for this task.

## References 
Papers
Attention Is All You Need
BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding
RoBERTa: A Robustly Optimized BERT Pretraining Approach
ELECTRA: Pre-training Text Encoders as Discriminators Rather Than Generators
DeBERTa: Decoding-enhanced BERT with Disentangled Attention
Libraries
https://huggingface.co/docs/transformers/
https://rajpurkar.github.io/SQuAD-explorer/
https://huggingface.co/docs/datasets/
