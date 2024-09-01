**# Structiure-is-All-You-Need**
In this research work we propose a way to reduce uncertainty in AI models by using structured data and ontologies. Traditional AI models often rely on probability, which can create uncertainty and make it hard for them to reason like humans. To solve this, we use ontologies—structured networks that organize data and to improve the model's reasoning skills. We also explore a novel approach using ontologies to aid RAGs and overcome hallucinations that is often faced by LLMs. 


**Architecture Diagram of proposed system**:
![image](https://github.com/user-attachments/assets/eec5eab6-859a-44d2-b871-2f827ab4d496)


First, we use a pre-trained BERT model to match similar concepts across different ontologies. This process, called ontology alignment, helps the model better understand the relationships between different ideas, making it more accurate and faster at learning compared to a regular model.This is considered as a synonyms classification task where we check if class c in ontology O and class c ′ in ontology O′ are synonymous to each other. We let a pre-trained BERT model, which is essentially a model that is trained to perform sequential classification, predict if a particular class pairis synonymous or not. We then show how this improved model can be used for tasks that involve classifying sequences of data, demonstrating that it reaches high accuracy faster than a standard model. **Note: this research project has been experimented with both BioClinical BERT as well as bert-base-uncased-yelp-polarity models**

Figure below shows the the accuracies of extremely fine-tuned and native model versions of both BioClinical BERT and bert-base-uncased-yelp-polarity models. Analyzing the accuracy after every epoch, it can be inferred that the rate of learning of the model trained through ontology alignment is much higher:

![image](https://github.com/user-attachments/assets/2468e697-c5ab-4d58-b61f-5c291eeb150e)

We then compare across both the pre-trained model and the model trained with ontologies, herewith referred to as the extremely fine-tuned model, named so due to the mode of data provided to fine-tune. We train the models over the same dataset to check how well and quickly the models are able to capture dependencies during training with the 
same model parameters θ. With qualitative and quantitative results our idea is to define a new Machine Intelligence hypothesis to show how important structured data is for a model.** We therby propose our hypothesis : "Consider two models α and β. Let model α be an extremely fine-tuned model with additional ability acquired through structured data and model β be the native version of model α. Both the models are bound to reach an optimal accuracy state S provided the models run for an arbitrary number of epochs ε. The factor deciding the better model in such a case would be the rate ρ at which a model reaches such an S. "
**

Finally, we explore how the relationships between concepts (where one concept is a subset of another) from the ontology alignment can improve AI systems like chatbots (LLMs). By adding these relationships to the prompts given to the model, we help it retrieve more relevant information, leading to better and more accurate responses. This makes chatbots smarter and easier to use without needing extra input from users.
