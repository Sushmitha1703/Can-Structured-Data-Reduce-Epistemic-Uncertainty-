
# Can Structured Data Reduce Epistemic Uncertainty? 
This repository contains the work related to the paper titled **Can Structured Data Reduce Epistemic Uncertainty?** which has been selected for presentation at *Next-Generation Language Models for Knowledge Representation and Reasoning* workshop, to be held at KR 2024 which will be held on November 4th 2024 at Hanoi, Vietnam.

## Goal of this work
This work aims to demonstrate: 
- How ontologies can be used to fine-tune language models, that are usually reliant on large amount of data. We show such a fine-tuning process makes the model learn at a higher rate, hence reducing epistemic uncertainty.
- How subsumption mappings obtained through ontology alignment can be used to aid RAGs and reduce hallucination that is often faced by LLMs. 

_Note: For our research purpose we have taken medical domain as our use case, the ontologies used are The Symptoms ontology and CSSO-Clinical Signs and Symptoms Ontology and the dataset used for classification is MedQandA benchmark dataset. We have experimented with both BioClinical BERT as well as bert-base-uncased-yelp-polarity._


## Architecture Diagram of proposed system
![image](https://github.com/user-attachments/assets/eec5eab6-859a-44d2-b871-2f827ab4d496)

## Our hypothesis 
_"Consider two models α and β. Let model α be an extremely fine-tuned model with additional ability acquired through structured data and model β be the native version of model α. Both the models are bound to reach an optimal accuracy state S provided the models run for an arbitrary number of epochs ε. The factor deciding the better model in such a case would be the rate ρ at which a model reaches such an S. "_

## List of contents in this repo
- **BERTMap**: Used to align two ontologies and extract the corresponding equivalence mappings.
- **BERTSub**: Used to retrieve subsumptions between to ontologies.
- **BioClinical BERT Classification**: Classification using BioClinical BERT, fine-tuned on an ontology alignment task.
- **bert-base-uncased-yelp-polarity Classification**: Classification using bert-base-uncased-yelp-polarity, fine-tuned on an ontology alignment task.
- **Generative Language Model using RAG**: Proposed method for enhancing RAG with subsumption mappings. The subsumptions are infiltrated to the prompt of the model. _Note: This is just an example of codebase for this module._

## Acknowledgement 
For our experimentation, we make use of the **DeepOnto framework** while aligning ontologies. DeepOnto is a Python package developed specifically for ontology engineering. It offers various tools for ontology reasoning, verbalization,normalization, and projection. It also supports ontology alignment as well as the completion of tasks using pre-trained LLMs. 


## Results
Figure below shows the the accuracies of extremely fine-tuned and native model versions of BioClinical BERT models. Analyzing the accuracy after every epoch, it can be inferred that the rate of learning of the model trained through ontology alignment is much higher. Similar results were obtained with bert-base-uncased-yelp-polarity model as well:

![image](https://github.com/user-attachments/assets/2468e697-c5ab-4d58-b61f-5c291eeb150e)

More results available in our paper that is to be out soon!
