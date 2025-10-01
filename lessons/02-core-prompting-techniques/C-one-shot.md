# One Shot Prompting

Another common prompting technique is called one-shot, which really simply means providing one example.

So we had zero-shot (zero examples) and now one-shot (one example).

This technique really leverages the model's ability to generalize from minimal data. Think of this as something that you might do with a coworker while pair programming or in a code review. You might see some code and be like...well actually if you look at this prior example, you can see how we did this and now make this new thing based on that prior art.

One shot is really efficient because you aren't trying to think of every edge case and every possibility, but its also going to be more reliable than hoping zero-shot understands your full intent.

Simple patterns are great for one shot prompts, where one example clearly shows what we are looking for. Also if you're working with straightforward transformations or if you're trying to work quickly and don't have the time to work through a bunch of really good examples, still providing an example will be helpful to the model over providing nothing.

> Note:
> - choose your example carefully because it sets the pattern
> - make your example the majority representative, don't pick an edge case
> - include all elements you want in your output
> - combine with explicit instructions for any additionally needed clarity
> - don't overcomplicate your example to cover every case, the model will generalize that pattern

An example of a one-shot prompt:
```
Write an engaging introduction for a blog post about remote work productivity.

Example:
Topic: Benefits of morning exercise
Introduction: "Picture this: It's 6 AM, your alarm goes off, and instead of hitting snooze, you lace up your sneakers. Sound impossible? Here's the thing—those who exercise before breakfast report 23% higher energy levels throughout their workday. But the real secret isn't just the exercise itself; it's what happens to your brain chemistry in those precious morning hours."

Now write an introduction for: Remote work productivity tips
```

Something we can add to our prompt library is a rating feature, with stars from 1-5. Here is an example of a one-shot prompt to get the model to design that new feature:

> Note: you will likely need to prompt the model again to build the feature after sending this prompt. This prompt uses an example to help the model "architect" this feature. Go through what it wants to build, prompt to make any adjustments you see fit, and then prompt the model to "build this feature" (or however you want to word it!)

```
You are helping develop a prompt library application. Here's an example of how to analyze and implement a new feature:

**EXAMPLE:** Feature Request: "Add a favorites/bookmarking system"

Implementation Plan:

1. **User Story**: As a user, I want to mark prompts as favorites so I can quickly access my most-used prompts without scrolling through the entire library.
2. **Technical Requirements**:
    - Add a heart/bookmark icon to each prompt card
    - Store favorite status in localStorage or database
    - Create a filter to show only favorited prompts
    - Visual indicator when a prompt is favorited (filled vs outlined icon)
3. **Code Structure**:

javascript
// Data model update
prompt = {
  id: 'prompt-123',
  title: 'Marketing Email Generator',
  content: '...',
  isFavorite: false,  // New field
  createdAt: '2024-01-15',
  rating: 4.5
}

// Toggle favorite function
function toggleFavorite(promptId) {
  const prompt = prompts.find(p => p.id === promptId);
  prompt.isFavorite = !prompt.isFavorite;
  saveToStorage(prompts);
  updateUI();
}

4. **UI/UX Considerations**:
    - Place favorite icon in consistent location (top-right of card)
    - Use intuitive icons (heart or star)
    - Provide visual feedback on click (animation/color change)
    - Add "Favorites" filter tab in navigation

---

**YOUR TASK:** Analyze the following feature request using the EXACT same format as the example above (User Story, Technical Requirements with bullet points, Code Structure with JavaScript examples, and UI/UX Considerations).

Feature Request: "Add a 5-star rating component to rate prompt effectiveness"
```
