# Delimiters/XML

If you don't know what a delimiter is, we use them every day...commas, periods. You use them in code to separate items in your arrays. They are at its simplest just like a boundary between a section of text. If you've seen markdown formatting, that's a great use of delimiters.

The same way that using bullet points on slides can make it easier for people to digest the information when you teach, LLMs can really benefit from having clear sections that the model can distinguish.

It doesn't actually matter what delimiter you choose, you can even make up your own and use them, but just make sure that you are being consistent and clear.

By using delimiters and XML tags, we can take large chunks of prompts and data, and break it up into easy to understand prompts for the model, the same way we look at a news article and see like there's a headline and a subheading and main content and some content with the research, but we understand their importance differently becasue of that visual hierarchy, and that is similar for LLMs.

You should use these any time you have a complex prompt, so you'll likely use these often.

Let's say we wanted to learn how to turn our application into a live production app, but we don't really know how and what considerations we need to keep in mind.

Let's use delimiters to ask our LLM to help us plan what those next steps would be:

```
I need to research how existing tools handle prompt management and version control to inform architecture decisions for a prompt library I'm building and hoping to move to production. Please research and analyze different approaches using this structure:

<research_area>
<topic>Prompt Management Solutions</topic>
<questions>
- What tools currently exist for prompt library management?
</questions>
</research_area>

<research_area>
<topic>Collaboration Features</topic>
<questions>
- How do teams share Postman collections or Insomnia workspaces?
- What permission models exist in developer tools?
</questions>
</research_area>

<research_area>
<topic>Technical Implementation Details</topic>
<questions>
- What databases do similar tools use (research from their engineering blogs)?
- How do they handle search at scale?
- What's their approach to data export/import?
- How do they prevent abuse and implement rate limiting?
</questions>
</research_area>

For each research area:
1. Find concrete examples from real products
2. Identify patterns across successful tools
3. Highlight common failures or user complaints
4. Estimate implementation complexity

Then synthesize this into:
- A competitive analysis matrix
- Recommended features for our MVP vs future releases
- Technical decisions informed by market research
```
