# Zero Shot

Zero-shot prompting is our baseline, and its going to look very similar to our standard prompt.

Zero-shot prompting means we are asking the model to do something without providing any examples of the task. We are relying on the model's training data to help us figure out what we want.

So what's the difference between this and the "standard prompt"?

All zero-shot prompts are standard prompts, but not all standard prompts are truly zero-shot. 

Don't get too far into the weeds trying to figure out the difference, just know zero-shot prompts don't provide examples, and you probably write these types of prompts without knowing it.

When do we want to use these?

We want to use zero shot prompting on anything simple that the model is going to be able to do without examples. When we are asking these models to solve basic tasks for us, whether they are tasks that are writing code, proofreading, maybe we made an AI application and want to evaluate customer feedback, anything that the model will have seen plenty of in its training data, we can try a zero-shot prompt for.

An example of a zero-shot prompt:
```
Classify the customer rating into neutral, negative or positive.

Text: The product was okay. It worked, but wasn't the easiest to understand how to use.
Sentiment:
```

We can see how this could be helpful in AI applications. We don't need to use tons of tokens for this generalized and very "smart" LLM to classify customer sentiment.

Now, use the zero-shot prompt below in a *new chat* (remember, our whole conversation history is reread every time we send a new note) to build a new scaffold with save/delete functionality for our prompt library project.

```
Create a prompt library application in HTML, CSS, and JavaScript.

Create an HTML page with a form containing fields for the prompt title and content

Add a save prompt button that saves to localStorage

Display saved prompts in cards

Each prompt card should show the title, a content preview of a few words, and a delete button

Deleting should remove the prompt from localStorage and update the display

Style it with CSS to look clean and modern with a developer theme

Include all HTML structure, CSS styling, and JavaScript functionality in their own files, but that can be run immediately and includes no other features.
```
