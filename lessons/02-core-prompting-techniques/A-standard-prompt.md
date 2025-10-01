# Standard Prompts

The first prompting technique is something you're *already* doing every time you use LLMs whether you know it or not!

Standard prompts are just asking direct questions or giving direct instructions to your AI assistant. This is just the official term that's used in academic papers and research.

The standard prompt isn't using any special formatting or techniques, just regular questions like "Write me a JavaScript function to sort an array and remove duplicates", or "Explain to me why thunder is so scary", or "When did the video game Apex Legends release?" Straightforward questions and commands. Nothing fancy! Try these for yourself in your favorite AI companion (I am personally a huge fan of using Claude in the browser for these!)

But this is the basis and the first building block of every subsequent kind of prompt. And here's something important to consider - this works exactly like asking a friend a question. If you ask a vague question, you get a vague answer. If you ask a precise question, you get a precise answer. The model works with what you give it, same as any human you walk up to today and ask a question to. 

Think about if you were to ask a coworker for help on your codebase. If you were to say to them "this doesn't work", they might guess at why and could be write but could be off because they have no *context* to what's wrong. But if you're like "hey, on line 56 when I passed in an empty array to this function, I got an error that says..." they can help you a lot better.

As part of this course, we are building an HTML/CSS/JS local prompt library where we can write a prompt, send it to the AI of our choosing, and use the output code to simply "vibe code" this project.

So now a note on this. As this is going to involve a lot of lines of code and prompts that adjust lines of code as we go, I suggest experimenting with Cursor, Copilot, or Claude Code for these prompts. You are welcome to use ChatGPT or Claude in the browser, but you'll have to copy/paste your code every time, which isn't convenient, more prone to errors and rate limits, and can take a lot of time.

So to see an example of a standard prompt in writing code, let's ask our AI assistant to write some code for us:

```
Create a prompt library application that lets users save and delete prompts.

Users should be able to:
- Enter a title and content for their prompt
- Save it to localStorage
- See all their saved prompts displayed on the page
- Delete prompts they no longer need

Make it look clean and professional with HTML, CSS, and JavaScript.
```

Your output will be different than mine (remember models are non-deterministic!) but depending on the model and provider, it may be very different than what I generated.

One thing you may notice when doing this is often your assistant will add additional features it wants to. It makes a lot of *assumptions* which introduces a lot more *randomness* than we want if we are going to use these models to generate code for us.

So, as an FYI, I deleted this scaffold for the project and will regenerate it in the next section.

But we can see these standard prompts already are pretty powerful! Now, let's add some technique to our prompts.
