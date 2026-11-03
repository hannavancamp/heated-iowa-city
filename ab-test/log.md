# A/B Test Log

## November 3, 2026, setup recorded before trial 1

- Every trial runs in claude.ai in Hanna's signed-in account, each in its own new incognito chat. Incognito chats stay out of chat history and do not use saved memory, so no trial can see any other trial.
- The model is Claude Sonnet 5.5, chosen in the claude.ai model menu, with the effort setting left at Medium, the app's recommended default. Every trial uses this same model and setting. This is how the plan's "default settings" is carried out, as a claude.ai chat with the app's normal settings rather than a bare API call.
- The page text was taken from the live pages on November 3 using the browser's visible-text method, the same way for both versions. The two texts differ only in the opening paragraph.
- The full prompts are saved as ab-test/prompt-a.txt and ab-test/prompt-b.txt. Each is the plan's prompt word for word, followed by that version's page text.
- Trials run in the order listed in ab-test/assignments.csv, starting November 3, which meets the plan's start date of no later than November 10.
- Claude (Anthropic) runs the trials through Hanna's browser at her direction, pasting each prompt and copying each full answer into ab-test/results.csv.
