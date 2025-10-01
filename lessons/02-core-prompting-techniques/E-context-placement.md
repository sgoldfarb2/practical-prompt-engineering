# Context Placement

Something else we need to consider, especially as context windows get larger and applications get larger (and chats get longer) is context placement.

[Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/pdf/2307.03172) analyzed the performance of language models with multi-document questions and also key-value retrievals. Huh?

Basically, they gave the models a ton of documents and asked it questions about some of the content within the documents, and moved where the document with the relevant information was. Sometimes it was at the beginning, other times in the middle, other times at the end.

What they found was that even though these models are able to get bigger and bigger context windows and handle more tokens, the LLMs did not make use of information in the long input contexts.

In fact, performance for the LLMs were highest when the information was placed at the beginning of the context and at the end of the context (though the beginning *was* better than at the end).

But here's where things got really weird.

nformation that was in the middle of many documents not only had worse performance than when the information was at the beginning or the end of the document, but actually the model often *performed worse* than its performance when predicting the answer with *no documents*.

This means that even though these models have bigger and bigger context windows that we are able to use, that means that information we give in context in the middle is sometimes literally getting lost to the model in all the context.

So this means when we have really important conversations, its really important that we place the most critical information to our context first, and any important additional information last to make best use of the model, and what belongs in the middle is the less important stuff.

This also means when your chats get really long (or your customer's chats), context may not only "fall off" if you fill the context window, but context in the middle might also get "lost" to the model.

Basically, this shows us that we need to start new chats when possible. Keep context small when you can. Position context at the front if its incredibly important, and if something else important comes up, add it to the end.

