# What are Large Language Models

Large Language Models refer to large, general-purpose language models that can be pre-trained and then fine-tuned for specific  purposes
##### Large Language Models are  trained to solve common language problems like:
- Text Classification
- Question Answering
- Document Summarisation
- Text Generation

## Breakdown
**Large:**
- Large training dataset
- Large number of parameters: Basically the memories and the knowledge of the model trained
**General Purpose:** It refers to when the model is sufficient to solve common problems. 
- Commonality of human language
- Resource restriction
**Pre-trained and fine-tuned**: Pre-train a large language model for general purpose with a large data set and then fine tune it with specific aims with a much smaller data set.

### LLM use cases:
- A single model can be used for different tasks. They are trained with petabytes of data and generate billions of parameters are smart enough to solve different tasks including:
	- Language Translation
	- Sentence Completion
	- Text Classification
	- Question Answering
	- And more
- LLMs Require minimal field training data so that we can tailor them to solve specific problems. We can obtain decent results even with little domain data.
	- They can be used for both **few-shot** or **zero-shot** scenarios
		- Few-shot: Training a model with minimal data
		- Zero-shot: The model can recognize things that have not explicitly been taught in the training
- Their performance is continuously growing as we add more data and more parameters
	- Large language models are almost exclusively based on [[Introduction to Generative AI#^8ff7e3|Transformer]] models.
### LLM Development vs Traditional Development

**LLM**:
- No ML expertise needes
- No training Examples
- No need to train a model
All we need to do is to think about prompt design

**Traditional ML**:
- ML expertise needed
- Training examples needed
- Meed to train a model
- Computing time + hardware
We need to think about minimizing a loss function

# Prompt Design
Prompt design and prompt engineering are two closely related concepts in natural language processing (NLP). Both require the creation of a prompt that is clear, concise and informative
But there are some key differences between the two:
#### Prompt Design
It is the process of creating a prompt that is tailored to the specific task that the system is being asked to perform.
#### Prompt engineering
It is the process of creating a prompt that is designed to improve performance. This may involve using domain specific knowledge, providing example of the desired output or using keywords that are known to be effective for the specific system.
####
In general, prompt design is a more general concept while prompt engineering is a more specialized concept.
Prompt design is essential while prompt engineering is only necessary for systems that require high  degree of accuracy or performance.

# Types of LLMs:
- Generic Language Models
- Instruction Tuned Models
- Dialog Tuned Models
Each need prompting in a different way:

### Generic(or raw) Language Models: 
Predict the next word (technically, token) based on the language in the training data
For example:
![[Screenshot 2024-09-05 at 6.15.46 PM.png]]
### Instruction Tuned Models:

^d06e71

Trained to predict a response to the instructions given in the input.
![[Screenshot 2024-09-05 at 6.17.46 PM.png|300]]
### Dialog Tuned Models
Trained to have a dialog by predicting the next response
- They are a special case if [[#^d06e71|Instruction tuned]] where requests are typically **framed a a question** to a chat bot
- Dialog tuning is a further specialization of instruction tuning that is expected to be in the context of a longer back-and-forth conversation, and typically works better with natural question-like phrasing.
# 
A model that can do everything has practical limitations. However, through task-specific tuning can make LLMs more reliable.

Vertex AI proved task-specific foundation models.

### Tuning
Tuning a model enables you to customize the model response based on examples of the tasks that we want the model to perform.
It is the process of adapting a model to a new domain or set of custom use cases by training the model on new data. 

### More efficient methods of tuning
Fine-tuning a model is very expensive:
#### Parameter-efficient tuning methods(PETM):
Methods for tuning an LLM on your own custom data without duplicating the model. The base model itself is not altered instead a small number of add-on layers are tuned which can be swapped in and out at inference time.
-  **Prompt Tuning:** One of the easiest parameter-efficient Tuning methods
### Vertex AI studio
- Quickly explore and customize GenAI models
- Developers can create and Deploy
features:
- Library of Pre-trained models
- Tool for fine-tuning models
- Tool for deploying models to production
- Community forum for developers to share ideas and collaborate
