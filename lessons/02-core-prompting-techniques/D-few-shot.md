# Few Shot Prompting

Now we can assume that if zero-shot prompting was zero examples, and one-shot prompting was one example, then few shot prompting is going to mean two or more examples.

And why would we want to do this?

[Language Models are Few-Shot Learners](https://arxiv.org/pdf/2005.14165) researched these prompts and proved that few-shot examples dramatically improved LLM performance. Also in the paper, there was evidence that while zero shot and one shot got more effective with model size, few shot seemed to increase more rapidly in accuracy as models got larger. Its definitely worth a read, or at least check out the graphs on how much better prompting can get with zero, one, and a few shots.

So when should we use few-shot prompting?

When we have complex patterns with multiple variations, classification tasks with multiple categories, when we want to standardize formats across a diverse array of inputs, when we have domain specific tasks that require context, and when consistency across varied outputs is really important.

> Note:
> - diversity in examples matters
> - include edge cases and failure cases
> - keep examples concise but complete
> - test in a few different chats with a few different number of examples to find what works best

An example of few-shot prompting:
```
Analyze the business decision with the requested level of detail.

Decision: Opening a new store location
Analysis Level: Quick take
Response: New location appears viable given foot traffic data and competitor absence, though initial investment is substantial.

Decision: Switching software providers
Analysis Level: Standard review
Response: Migration offers long-term cost savings of 30% and better feature set. However, switching requires 2-month transition period with potential disruption to operations. Staff training needed but vendor provides support. Recommend phased rollout starting with non-critical systems.

Decision: Launching a new product line
Analysis Level: Comprehensive assessment
Response: Market analysis indicates strong demand with 40% of surveyed customers expressing interest. Competitive landscape shows opportunity for differentiation through our unique manufacturing process. Financial projections suggest break-even within 18 months, with 25% profit margins by year 3. Risk factors include supply chain dependencies on single vendor and need for $2M initial investment. Manufacturing capacity exists but requires equipment upgrades. Marketing strategy should emphasize sustainability angle based on focus group feedback. Recommend soft launch in Q2 with limited geographic rollout, expanding nationally in Q4 based on performance metrics. Success criteria: 10,000 units sold in first quarter, customer satisfaction above 85%, and return rate below 5%.

Decision: Implementing remote work policy
Analysis Level: Standard review
Response:
```

For our prompt library, we want to add a "notes" feature that allows us to add notes to our prompts, in case we want to say "worked better with this model" or add the technique we used or something like that!

 > Note: you will likely need to prompt the model again to build the feature after sending this prompt. This prompt uses an example to help the model "architect" this feature. Go through what it wants to build, prompt to make any adjustments you see fit, and then prompt the model to "build this feature" (or however you want to word it!)

```
I need you to create a prompt for implementing a new feature. Here are examples of effective feature implementation prompts:

**EXAMPLE 1: Save/Delete Functionality Prompt**
Create a save and delete system for a prompt library application with the following requirements:

Technical Specifications:
- Save button that persists prompts to localStorage
- Delete button with confirmation dialog before removal
- Visual feedback on successful save (green checkmark animation)
- Trash icon with hover effect for delete action
- Auto-save indicator when changes are detected

Provide complete HTML, CSS, and JavaScript with:
1. Semantic HTML with data attributes for prompt IDs
2. CSS animations for save confirmation and delete hover states
3. JavaScript with proper event delegation for dynamically added prompts
4. localStorage integration with JSON serialization

The system should work with this data structure:
const prompts = [
  { id: 'prompt-001', title: "Blog Writer", content: "Generate blog posts...", savedAt: Date.now() }
];

Include error handling for localStorage quota exceeded and implement a "Recently Deleted" temporary storage (up to 5 items).

**EXAMPLE 2: Star Rating Component Prompt**
Build a 5-star rating system for rating prompt effectiveness with these specifications:

Core Requirements:
- Interactive 5-star display (click to rate, hover to preview)
- Half-star precision (4.5 stars possible)
- Shows average rating and total number of ratings
- Updates immediately without page refresh
- Allows users to change their rating

Implementation Details:
- SVG stars for crisp display at any size
- Gold fill for rated, gray outline for unrated
- Smooth hover animations (scale and glow effect)
- Display format: "4.5 ★ (23 ratings)"

Deliver production-ready code including:
1. HTML with accessible ARIA labels for screen readers
2. CSS with star animations and responsive sizing
3. JavaScript for rating logic and state management
4. Comments explaining calculation methods

Data model to support:
{
  promptId: 'prompt-001',
  ratings: [5, 4, 5, 3, 5], // Array of all ratings
  userRating: 4, // Current user's rating
  averageRating: 4.4
}

**YOUR TASK:** Based on the examples above, create a detailed prompt for building a "notes section" feature where users can add, edit, save, and delete notes for each prompt in the library.

The prompt should follow the pattern shown in the examples:

- Clear feature description
- Specific technical requirements
- Implementation details
- Expected deliverables
- Data structure/integration notes

Keep it as simple as possible to create a working notes section with only the features mentioned in your task.
```
