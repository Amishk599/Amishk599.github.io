---
title: "Understanding AI Jargons"
date: 2025-02-09T12:00:00+05:30
draft: false
tags: ["AI", "ML"]
categories: ["Tech"]
summary: "Simply understanding some common AI jargons that float around"
showToc: true
TocOpen: true
---

### Base Model
It is huge neural network which is trained on entire data available on the internet. it’s main objective is to complete text. At this stage it is not very impressive or useful. It is just a first step toward modern LLMs that we as end users are used to interating with (called Chat Models)

### Chat Model
It is an AI assistant which is fine tuned to interact with users in a useful, structured and context aware manner (example ChatGPT). It is trained to understand and follow instructions, answer targeted questions and assist in a meaningfull manner unlike a Base Model that simply predicts and completes text. A Base Model can be transformed into a Chat Model by :<br>
1) **Supervised Fine Tuning (SFT)** : Based mode is trained on high quality examples of human demonstrations.<br>
2) **Reinforcement Learning from Human Feedback (RLHF)** : Generated responses from the model are refined/optimized based on human rating.

Note : Generally, SFT is followed by RLHF.


#### Supervised Fine Tuning (SFT)
It transforms a Base Model into a Chat Model. This is achieved by training the base model on carefully crafted high quality human written conversation. Basically a humans forms some questions and write a perfect answer! This way humans create a huge dataset **(human crafted dataset)** of such conversations or dialogues which basically guides it to follow instructions, give meaningful answers and engage the user meaningfully.

#### Reinforcement Learning from Human Feedback (RLHF)
This is generally followed after SFT where the LLM, now capable of giving meaningful answers, is oriented  / refined to suit human prefrences so that final response is more accurate and natural and safe. Unlike normal Reinforcement Learning which is good for cases like training a model to play a game - where it gets reward for a win and penalized for a loss, but in this case of LLM answering a question, it is quite tricky to define a reward / penalty system; that is where RLHF comes in, which is a clever way to improve performance. It works like so 

1) LLM generates multple responses for a user’s prompt
2) Humans rank these responses from best to worst (based on correctness, quality, format, etc)
3) Above step is slow and hard to achieve at scale so a seperate model is trained **(Reward Model)** to do predict response rankings like humans.
4) After Reward Model is ready is it used to fine tune the LLM using reinforcement learning.
5) The end result is an Chat Model

### Reasoning Model
They incorporate an intermediate step between receiving a question and answering. Unlike a Chat Model they simply don’t go from Question to Answer by predicting it, instead they include a step for thinking **(Question —> Think —> Answer)** through the problem before responding. The thinking or reasoning step allows them to break down complex problems and explain their thought process. (example, ChatGpt-o3 and DeepSeek-R1). These resoning model are particularly good with coding, puzzle solving, mathematical problems, etc. Some cons of these reasoning models are:

+ Have a higher inference time.
+ Have a higher computational cost associated with their responses.

A normal LLM / Chat Model can be encouraged to reason step by step through simple prompt engineering technique called **Chain of Thought**. Which makes the model to generate intermediate reasoning steps before infering. Simple trick involves adding **“Let’s think step by step”** to the prompt.



