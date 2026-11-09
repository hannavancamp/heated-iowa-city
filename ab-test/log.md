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

## November 5, 2026, change after the trials

- Version B (try-it-free-b.html) was given its own title tag and meta description, because the updated Deliverable 3 handout requires a unique title and description on every page and version B had copied version A's. The new title is "Free Hot Yoga in Iowa City, Test Version B | Heated."
- This does not affect the results. The AI visitors were shown only the visible page text, which is unchanged, and the title tag and meta description were never part of the prompt.

## November 6, 2026, test redesigned before any new data

- Professor Nozari replied to my approval request that the opening paragraph treatment was not clear, because a rewritten paragraph changes several things at once.
- I replaced it with a headline-only test. Version B (try-it-free-b.html) now matches version A except for the H1, which reads "Free Hot Yoga in Iowa City for University of Iowa Students." The opening paragraph went back to version A's wording.
- The revised ab-test-plan.md, a new random assignment list (ab-test/headline/assignments.csv, seed 20261106), and the exact prompts (ab-test/headline/prompt-a.txt and prompt-b.txt) were committed on November 6, before any trial of the new test.
- The November 3 opening paragraph trials (ab-test/results.csv) belong to the first design only and are not part of the headline test. They stay in the repository as a record.
- Trials for the headline test will start only after Professor Nozari approves the new design.

## November 9, 2026, headline treatment revised before any data

- Professor Nozari replied that "for University of Iowa Students" adds no new information, because "Iowa City" in the control headline already includes those students, and suggested a treatment that adds information the control does not have.
- Version B's headline now reads "Free Hot Yoga in Iowa City, No Membership Required." This is true on the page, since the free first class does not require a membership. ab-test-plan.md and ab-test/headline/prompt-b.txt were updated to match. The assignment list from November 6 is unchanged and still unused.
- The plan was due before November 9. This revision lands on November 9 only because it responds to his November 9 feedback on the version committed November 6.
- No trials of the headline test have run. They will start after Professor Nozari approves this treatment.

## November 9, 2026, approval recorded before trial 1

- Professor Nozari approved the no-membership headline treatment by email on November 9.
- The headline trials run the same way as the first test. Each trial is a new incognito chat in claude.ai with Claude Sonnet 5.5 at the Medium effort setting, the prompt is pasted exactly as committed, and trials follow the order in ab-test/headline/assignments.csv. Results go to ab-test/headline/results.csv.
