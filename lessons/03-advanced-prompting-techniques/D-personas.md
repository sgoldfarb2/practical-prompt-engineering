# Personas

A lot of people think that they make the model smarter by providing it with a persona, and that's not actually what is happening.

When you use words that describe who the model is role playing to be, you're already steering it in the direction of certain data that it has been trained on.

Let's say you're struggling with the model not being able to handle a database example. If you add to the beginning of your prompt "you are a database expert", now suddenly the model is reaching out in its "brain" to all the data that has to do with databases because it has that pattern matching, so now its reaching out to parts of its training data the considers indexes, normalization, query optimization, things that when it was trained on data, it saw a lot associated with databases and database experts.

Personas are of course great for tone and style, so maybe you don't need your GPT app to do some intense calculations, but you always want it to be pleasant and friendly and helpful instead of a no-nonsense consultant, adding that persona will help it adapt the right tone and style to the conversation.

If you give it a persona looking for a specific perspective it can be helpful, for example if you ask it to look at your codebase as a UX designer, you'll get a lot different answers than if you asked it to be a "security engineer".

Some good use cases for personas:

```
Code review: 'You are a senior engineer focused on security and performance'

Documentation: 'You are a technical writer who prioritizes clarity for beginners'

Debugging: 'You are a systematic debugger who checks assumptions'

Architecture: 'You are a solutions architect who considers scalability’”
```

I personally like to use it for learning new things. Maybe the model can role play as a JavaScript tutor or an AWS Architect who is also really good at explaining things to a five year old.

Adding too much to a persona can make the model's answers more rigid as well, so be careful making those _long_ personas that aren't adding much anyway.

When researchers analyzed model outputs, they found that personas primarily affect:

- Vocabulary selection (technical terms vs. plain language)
- Response structure (systematic vs. conversational)
- Error checking behavior (thoroughness)
- Confidence in assertions

> Note: you can change personas mid-conversation to get different viewpoints on the same problem.

An example of this if we were doing more research into getting our application live:

```
You are a Senior Engineer with experience building startups from zero to MVP.

Our prompt library currently runs entirely in the browser with localStorage. We're considering making it a production-ready tool that teams can use. Create a comprehensive technical specification that includes:

1. **System Architecture Document** that covers:
   - Data persistence strategy (evaluate PostgreSQL vs DynamoDB vs Firebase)
   - Authentication approach (OAuth, magic links, or API keys)
   - Real-time collaboration requirements
   - Rate limiting and abuse prevention
   - Search infrastructure (full-text search vs vector embeddings)

2. **API Design Specification** with:
   - RESTful endpoints vs GraphQL evaluation
   - Versioning strategy
   - Pagination approach for large prompt libraries
   - Webhook events for integrations

3. **Scaling Projections**:
   - Start with 100 users → path to 1M users
   - Cost per user at different tiers
   - Performance benchmarks to maintain

Use your experience to make opinionated recommendations. Write as if you're presenting to a junior engineering team.
```
