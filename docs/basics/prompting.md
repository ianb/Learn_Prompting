---
sidebar_position: 0
---
# Prompting

Before we get to Prompt Engineering, what is prompting? It can be defined as 
"converting tasks into a language model format"(@shin2020autoprompt). Slightly less
formally, it is the process of taking a task and converting it into a question that
can be answered by a language model. Here are two examples of this:

#### 1) Sentiment Analysis

If you are performing sentiment analysis on Tweets with the binary labels "positive" and "negative",
you can convert this into a language model format by posing the question "Is this tweet positive or negative?"

Your full prompt could look like this:

```
Tweet: "What a beautiful day!"

Is this tweet positive or negative?
```

#### 2) Math Word Problem Solving

If you have a dataset of mathematical equations that you would like a language model to solve,
you can convert this into a language model format by posing the question "What is EQUATION"

Your full prompt could look like this:

```
What is 100*100?
```

# Intro to Prompt Engineering

For this last prompt, GPT-3 (text-davinci-002) (@brown2020language) will actually answer 1,000 (incorrect). This is where
prompt engineering comes in. If, instead of asking `"What is 100*100?"`, we ask 
`"What is 100*100? Make sure your answer has the correct number of 0s:"`, GPT-3 will
answer 10,000 (correct). Why is this the case? Why is the additional specification 
of the number of zeros necessary for the AI to get the right answer? How can we create
prompts which yield optimal results on our task? This last question, in particular,
is the focus of the field of Prompt Engineering, as well as this course.

# Vocabulary 

We will cover basic vocabularly here, but frequently assume basic ML/NLP (natural language processing) knowledge. 

Although familiarity with LLMs and MLMs is mostly assumed,
we provide a short introduct to each concept here:

- Large Language Models (LLMs), Pretrained Language Models (PLMs)(@branch2022evaluating), Language Models (LMs), and foundation models

These terms all refer to the same thing: large neural networks, which have usually been trained 
on a huge amount of text.

- Masked Language Models (MLMs)

MLMs are a type of NLP model, which have a special token, usually `[MASK]`, which is
replaced with a word from the vocabulary. The model then predicts the word that
was masked. For example, if the sentence is "The dog is [MASK] the cat", the model
will predict "chasing" with high probability.

