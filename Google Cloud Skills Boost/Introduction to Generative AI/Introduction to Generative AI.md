 Generative is a type of artificial intelligence technology that can produce various types of content, including text, imagery, audio and synthetic data.

## AI vs ML
![[Gai-1.1.excalidraw]]
- AI is a discipline while Machine Learning(ML) is a sub-field of AI.
- ML is a program or system that trains a model from input data.
- The trained model can make useful predictions from new(never-before-seen) data drawn from the same one used to train the model
- This means that machine learning gives the computer the ability to learn without extensive programming.
## Types of ML models
Two of the most common ML models are **supervised** and **unsupervised** ML models.
The key difference between the two is that with ==supervised models we have labels.== -
- Labeled data is data that comes with a tag, like a name, a type or a number. 
- Unlabeled data is data that comes with no tag.
#### Supervised models
![[gai-1.2.excalidraw]]

- Testing data values are inputted into the model.
- The Model than output an output in comparison to the model used.
- If the predicted values and the actual training data values are far apart, it returns an error. 
- The model tries to reduce this error until the predicted and actual output values are closer together.

#### Unsupervised Models
![[Gai-1.3.excalidraw|200]]

## Deep Learning

It is a type of Machine Learning that utilizes artificial Neural Networks, allowing them to process more complex patterns than normal ML. These are inspired by the human brain.

- Like our brains they are made up of several inter-connected neurons/nodes that perform complex tasks. 
- Deep learning models typically have multiple layers of neurons, which allows them to learn more complex patterns than traditional ML models.
- Neural networks can use both labeled and unlabeled data. This is called **Semi-Supervised Learning**.
- In Semi-Supervised Learning a model is trained on a small amount of labeled data and a large amount of unlabeled data. The labeled data helps the network learn the basic concepts of a task, while the unlabeled data helps the neural network to generalize to new examples.

==Generative AI is a subset of Deep Learning==. Which means:
- It uses artificial neural networks.
- Can process both labeled and unlabeled data
- Uses Supervised, Semi-Supervised and Unsupervised methods.

LLMs(Large Language Models) are also a subset of deep learning.
##
Deep learning models or ML models in general can divided into two categories:
1. Generative Model
2. Discriminative Model

### Discriminative Models
- They are used to classify or predict labels for data points.
- They are typically trained on data set of labeled data points and the learn the relationship between the features of data points and the labels. 
### Generative Models
- It generates new data instances based on learned probability distribution of existing data.
- They generate new content.

## Generative AI
### What is and what is not GenAI?
![[IMG_0020.jpg]]

###
So traditional ML supervised learning process takes training code and labeled data to build a model. Depending on the use case, the model can give us a prediction, classify something or cluster something.

The Generative AI process can take training code, labeled data and unlabeled data of all data types and build a foundation model. The foundation model can then generate new content. It can generate text, code, images, audio, video etc.

So we can define GenAI as:
==Gen AI is a type of Artificial Intelligence that creates new content based on what it has learned from existing content.==

![[IMG_0019.jpg]]

## Transformers

^8ff7e3

The power of Generative AI comes from the use of transformers. 
At a high-level a transformer consists of an **encoder** and a **decoder**.
The **encoder** encodes the input sequence and passes it to the **decoder** which learns how to decode the representations for a relevant task.

Sometimes transformers run into issues, like "hallucinating".
Hallucinations are words or phrases generated by the model that are nonsensical or grammatically incorrect. These can caused by a number of factor such as:
- The model is not trained on enough data
- It is trained on *noisy* or *dirty* data
- Is not given enough context
- Or is not given enough *constraints*
*Hallucinations* make output text difficult to understand and make the model more likely to generate incorrect or misleading information.

## Prompts
It is a small piece of text that is given to a LLM as input and it can be used to control the output of the model in a variety of ways.
### [[Introduction to LLMs|Prompt Designing]]
It is a process of creating a prompt that will generate the desired output from the LLM. 

## Types of Gen AI models with text as input

1. Text-to-Text: These take Natural Language Input and generate text output. These Models trained to learn a mapping between a pair of text.(For example: Translating from one language to other)
2. Text-to-Image:  Trained with a large set of images, each captioned with a short text description. [[|Diffusion]] is one method used to achieve this.
3. Text-to-Video: Trained to generate a video representation from text input. 
4. Text-to-3D: Generate 3D objects that correspond to the user's text description. 
5. Text-to-Task: Trained to perform defined tasks or actions based on text input.
6. Foundation Model: A large AI model pre-trained on a vast quantity of data, designed to be adapted or fine tuned to a wide range of downstream tasks such as sentiment analysis.
![[IMG_0021.jpg]]
#### Vertex AI Studio
- Quickly explore and customize various GenAI
- Developers can create and deploy generative AI models
#### Vertex AI
 User friendly way to create various GenAI models such as:
 - Chatbots
 - Digital Assistants
 - Custom Search Engines
 - Knowledge bases
 - Training Applications, etc.


