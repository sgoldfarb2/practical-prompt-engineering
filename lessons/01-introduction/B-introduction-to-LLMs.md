# LLMs - A Brief Overview

Before we can learn any prompting techniques, we need to understand a very basic version and amount of how LLMs work.

I call this part: ***LLMs the Easy Parts***

LLMs are pattern prediction machines that generate one token at a time (for now, don't worry about what a token is, we will call them words for now)...so one word at a time. This means that there is no "planning ahead" for LLMs, they are "thinking" when they are typing. They are kind of similar to the autocomplete on your phone, but MUCH better, which we will talk about *why* shortly.

One other important thing to know first is that LLMs are non-deterministic.

Something that is deterministic is a calculator. Every time you input the same thing (2+2) you're going to get the same output (4). LLMs are not like calculators, they are non-deterministic. This means that even if you and I input the same exact content into the same exact model at the same exact time...we'd still get different answers. How much those answers differ can vary widely! Sometimes they'll look very similar and maybe be a word or two apart, but other times they'll be completely different!

You can try this for yourself to prove this - open 5 different chats with your favorite LLM (Claude, ChatGPT, Gemini, etc) and copy/paste the same prompt into each chat. You'll see the differences!

Why do we care though?

Being non-deterministic is important for us to know, because it means there is some *randomness* in responses, so we have to account for that and try and minimize that randomness. We also can get inaccuracies in this randomness, and want to minimize those.

On to what I would call: ***LLMs the Medium Parts***

Back in 2017 (which feels like forever ago!), Google published [Attention Is All You Need](https://arxiv.org/pdf/1706.03762) which was groundbreaking for the "Transformer Architecture". Before transformers, models were a lot like your phone's autocomplete, they could only track a few nearby words.

The breakthrough here was the "attention" mechanism that let's models figure out in a much larger content what actually matters for pattern prediction. Without getting too into the new architecture, just know that before this, autocomplete could track a handful of words. If you think about using your phones autocomplete, it starts out really great, but after adding a few words, the quality of the guesses goes down exponentially.

Now, with this new architecture, we could have hundreds, thousands of words being paid attention to. Models today have context windows (more on that later too) of even a million or more words (tokens technically).

And briefly, what I call ***LLMs the Hard Parts***

LLMs are neural networks, so they are inspired by how our brains work. Just like we can strengthen our neuron connections through practicing different things, LLMs adjust their *parameters* through training.

Training happens in pre-training and fine-tuning sections, and all you need to understand about that is sometimes when using open source models, we can use the "base" model and that's the model that has gone through pre-training without fine tuning. The fine-tuning stage makes these LLMs helpful assistants, so when you're talking to ChatGPT or Claude, you're getting that question/answer and conversational format that comes from the fine-tuning phase.

Something really cool to know? The entire model is just a parameter file and a few hundred lines of code for inference. That's all. The intelligence is in those billions of parameters. Pretty incredible, huh?