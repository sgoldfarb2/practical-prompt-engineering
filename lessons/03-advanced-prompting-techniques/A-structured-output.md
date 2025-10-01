Structured Output

Structured output is really about getting consistent and usable formats the first time. And while this may feel and seem like something that's more work for us and takes more time, if you think about the amount of time you've spent copy/pasting and reformatting your output and you do that a few times a day, suddenly spending a few minutes to make a structured output prompt can save you hours.

This is also really important when it comes to production code, especially if you're using LLMs to generate code or generate content that you are passing down to other parts of your application. You aren't going to build into an AI application that maybe you'll get a response in paragraphs, maybe JSON, maybe bullet points, and do this for each of those. And even if you do, you'll end up getting some mixture that breaks.

So when should we use this?

Any time you need a specific format, any time you're generating multiple similar items like functions, tests, docs, data, etc. Maybe if you want to extract structured data from something that is unstructured like user feedback that was not used in the past, but now you want to present on your site.

Honestly also just use this when you're tired of reformatting your responses!

An example of structured output:
```
Extract the meeting details from this email.

Format like this:
Date: [date]
Time: [time]
Location: [location]
Topic: [topic]

Email: "Let's meet tomorrow at 2 PM in Conference Room B to discuss the Q4 budget."
```


And one that might be a helpful type of structured output to use in applications:
```
Convert this error into JSON. Return ONLY the JSON, no explanation.

"Error 404 occurred at 3:45 PM when trying to access /users/profile endpoint"
```

Now that we've seen how great structured output can be, let's use an example of a structured output prompt to create a metadata tracking system to track our model used, the date, and even a token estimator:

```
Create a metadata tracking system for a prompt journal web application that is attached to our prompts in our prompt library.

FUNCTION SPECIFICATIONS:
1. trackModel(modelName: string, content: string): MetadataObject
   - Accept any non-empty string for modelName
   - Auto-generate createdAt timestamp
   - Estimate tokens from content
   
2. updateTimestamps(metadata: MetadataObject): MetadataObject
   - Update the updatedAt field
   - Validate updatedAt >= createdAt
   
3. estimateTokens(text: string, isCode: boolean): TokenEstimate
   - Base calculation: min = 0.75 * word_count, max = 0.25 * character_count  
   - If isCode=true, multiply both by 1.3
   - Confidence: 'high' if <1000 tokens, 'medium' if 1000-5000, 'low' if >5000

VALIDATION RULES:
- All dates must be valid ISO 8601 strings (YYYY-MM-DDTHH:mm:ss.sssZ)
- Model name must be non-empty string, max 100 characters
- Throw errors for invalid inputs with descriptive messages

OUTPUT SCHEMA:
{
  model: string,
  createdAt: string (ISO 8601),
  updatedAt: string (ISO 8601),
  tokenEstimate: {
    min: number,
    max: number,
    confidence: 'high' | 'medium' | 'low'
  }
}

VISUAL DISPLAY:
Create an HTML/CSS component that adds and displays metadata in the prompt card:
- Model name
- Timestamps in human-readable format
- Token estimate with color-coded confidence (green/yellow/red)
- Sort by createdAt descending

CONSTRAINTS:
- Pure JavaScript only (no external libraries)
- Must work in browser environment
- Include try/catch error handling
```

