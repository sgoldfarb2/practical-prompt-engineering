# Temperature, Top P, Tokens, and Context Windows

**Temperature**: our way of changing a model's creativity or randomness

Temperature controls how predictable the AI outputs will be. This is a range from 0 to 2. At temperature 0, the LLM will *always* pick the most likely next word (remember, they are pattern predictors, so their responses are just picking words based on computer science and statistics).

When we raise the temperature, the AI might pick the 2nd most likely word, or the 100th most likely word. This can make our outputs much more creative, but can also add too much randomness and make them incoherent.

This setting is *unavailable* to us when we are using ChatGPT or Claude in chat, or in Copilot or Cursor, but when we are building API applications, we have the opportunity to adjust this temperature. This is why we must understand what it is, because if you decide to create an AI application after this, you may need to adjust this setting!

If you are writing an application focused on creativity, you might bump the temperature up to 1.4 (remember 2 is completely random and incoherent). But if you are running a medical AI application, you might dial it way down to .5. So keep this in mind when working with these APIs.

**Top P**: Top P *sounds similar* to temperature, but it does something a bit different.

In every word prediction, the percentage of words that can be predicted add up to 100%. So if I ask the color of the sky, "blue" might be 80% most likely, "gray" 15% most likely, and "orange" 5% most likely. We can see that these three options add up to 100%.

But we can *change* this setting.

If we are running a business and want to only consider the top 90% of options, we can change our top p to .9, and it will only consider the first 90% of token/word options. What does that mean for our sky example? That "orange" would no longer be considered, because its not in the top 90% most likely next words.

This is another way we can control some of the randomness within our application, and we can use these together to make our application as fine-tuned towards or away from creativity as we want.

Again, this is not something we can edit while just chatting with these models, but in AI applications, we *can* change these. And its important to understand really how LLMs are genuinely just predicting next tokens for our upcoming prompt techniques.

**Tokens**: like words...but not.

Okay, now I can finally stop saying words/tokens and just explain what I mean!

Tokens are to the model what words are to humans. Tokens are roughly .75 words, but not always! Weirdly enough "JavaScript" might be one token but "javascript" might be two. We aren't here to figure out what is an exact token. All we need to understand about tokens is that they are the words/code/etc. that the model is being input or putting back out to us.

**Context Windows**: how many tokens an LLM can "remember" at a time.

So now that we know what a token is, let's talk about context and context windows.

LLMs have no memory. I know, it seems like they do...so how does this work?

Every time you enter an input to the LLM, it responds, and then that whole chat history is sent to the LLM again. So every time you send a message, you don't see it, but ALL your past messages are also being sent to the LLM. All your inputs, all the LLMs outputs (within that chat).

So this is how LLMs "remember". By just...rereading the whole conversation over and over again.

But at some point, the LLM is going to run out of "memory" and that's the context window - the amount of tokens that the LLM is able to remember.

It's important to understand this because in these prompting techniques, we will be utilizing context windows and learning about when to open new chats and restart those windows.

Its important to also know that *context windows can hit their limit without you knowing*.

When you hit these limits, the oldest context (so your first inputs/outputs) drop off first. First in, first out. But the model will not tell you this happened! So if you're having a conversation and now the model doesn't remember what you said at first...like maybe..."this is the MOST IMPORTANT STRUCTURE IN MY APP", and you run past that context window, that context is gone. Lost. Without you knowing. While models now have pretty large context windows, this is still an important concept to understand as we move through our prompting techniques today.