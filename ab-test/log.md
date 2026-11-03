# A/B Test Log

## November 3, 2026, setup recorded before trial 1

- Every trial runs in claude.ai in Hanna's signed-in account, each in its own new incognito chat. Incognito chats stay out of chat history and do not use saved memory, so no trial can see any other trial.
- The model is Claude Sonnet 5.5, chosen in the claude.ai model menu, with the effort setting left at Medium, the app's recommended default. Every trial uses this same model and setting. This is how the plan's "default settings" is carried out, as a claude.ai chat with the app's normal settings rather than a bare API call.
- The page text was taken from the live pages on November 3 using the browser's visible-text method, the same way for both versions. The two texts differ only in the opening paragraph.
- The full prompts are saved as ab-test/prompt-a.txt and ab-test/prompt-b.txt. Each is the plan's prompt word for word, followed by that version's page text.
- Trials run in the order listed in ab-test/assignments.csv, starting November 3, which meets the plan's start date of no later than November 10.
- Claude (Anthropic) runs the trials through Hanna's browser at her direction, pasting each prompt and copying each full answer into ab-test/results.csv.

## November 3, 2026, trial run

- All 100 trials ran on November 3 in one batch, in the order of ab-test/assignments.csv, starting at about 1 pm Central Time and finishing about 13 minutes later. The exact time of each trial is in ab-test/results.csv.
- Before each send, the runner confirmed that the model read Sonnet 5.5 Medium, that the chat was incognito, and that the text in the message box matched the committed prompt exactly. Every trial used its own new chat.
- All 100 answers began with a whole number from 1 to 7, so no trial was invalid, and none was rerun or dropped.
- No results were analyzed while the trials were running, nothing about the setup changed, and the run was not stopped early.
- To keep the file readable, results.csv names the prompt file used for each trial instead of repeating the 3,800-character prompt in every row. The committed prompt files hold exactly the text that was sent.
- The first commit of results.csv left a comma inside the interface column unquoted, which shifted the columns. A second commit on the same day quoted that field, and no trial data changed.
