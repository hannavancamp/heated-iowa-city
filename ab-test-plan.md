# A/B Test Plan, Free Hot Yoga Page Headline

MKTG:4400 Digital Marketing, Project Deliverable 3. Hanna Van Camp. Revised and committed November 6, 2026, before any data was collected for this test.

## Why this plan was revised

My first plan, committed November 2, tested a rewrite of the page's opening paragraph. When I asked Professor Nozari to approve it, he replied on November 6 that the treatment was not clear, because a rewritten paragraph changes several things at once. I replaced it with this simpler test, where one headline changes and nothing else does. The first plan, its trials, and its results stay in the repository history and in ab-test/ as a record. They are not part of this test.

## Page and treatment

The test runs on the free classes page (try-it-free.html). The treatment is the page's main headline (the H1). Every other part of the page is identical in both versions.

- **Version A (try-it-free.html)** keeps the current headline, "Free Hot Yoga in Iowa City."
- **Version B (try-it-free-b.html)** changes it to "Free Hot Yoga in Iowa City for University of Iowa Students."

Version B carries a noindex tag and a canonical tag pointing to version A, and it is left out of sitemap.xml, so it does not compete with version A in search.

## Hypothesis

Visitors shown version B will rate themselves more likely to book a free or intro class than visitors shown version A.

The reasoning is that the visitors in this test are University of Iowa students on a budget. A headline that names them signals right away that the page was written for someone like them, which should make the offers feel more relevant and more worth acting on. This prediction could be wrong. The rest of the page is identical and holds all of the actual offers, so one line at the top may not change how the visitor feels about booking.

## Visitors, prompt, and assignment

**Model.** Claude Sonnet 5.5, chosen in the claude.ai model menu, with the effort setting left at Medium, the app's recommended default. The same model and setting are used for every trial.

**Fresh conversation.** Each trial runs in its own new incognito chat in claude.ai. Incognito chats do not use saved memory and are not kept in chat history, so no trial can see any other trial.

**Page shown.** The full visible text of the page, taken the same way for both versions. The only difference between the two page texts is the headline line. The full prompts are saved as ab-test/headline/prompt-a.txt and ab-test/headline/prompt-b.txt.

**Exact prompt, identical in every trial except for the page text.**

> You are a University of Iowa student who has never tried hot yoga. You are curious about it but on a tight budget, and you just searched Google for "free hot yoga iowa city" and clicked on this page. Read the page below and decide how likely you are to book a free or intro class at one of the studios it describes.
>
> Answer on the first line with a single number from 1 to 7, where 1 means "definitely would not book" and 7 means "definitely would book." On the second line, give one sentence explaining your rating.
>
> PAGE:
> [full page text of version A or version B]

**Assignment.** The order of versions was generated before any trial with Python's random module (seed 20261106), shuffling exactly 50 A and 50 B assignments. The list is committed as ab-test/headline/assignments.csv, and trial N is run with the version listed in row N. Versions are mixed throughout the run rather than running all of A first.

## Outcome

The 1 to 7 rating on the first line of each response. A response that does not begin with a whole number from 1 to 7 is logged as invalid, kept in the raw data, and reported, never rerun or dropped.

## Sample size and timing

100 trials total, 50 per version. Trials start only after Professor Nozari approves this design, and no later than Tuesday, November 17, 2026. All 100 trials run before any results are analyzed, and the run is not stopped early.

## Comparison and what counts as support

The comparison is the mean rating in version B minus the mean rating in version A, tested with a two-sided Welch two-sample t-test (Google Sheets T.TEST with tails 2 and type 3) at a significance level of 0.05. The hypothesis is supported if version B's mean is higher and the p-value is below 0.05. A difference in the other direction, or a p-value of 0.05 or above, means the test does not support the hypothesis, and I will report that as the result.

## Records kept

Every response, the version shown, the model, and the date and time of each trial go into ab-test/headline/results.csv and a Google Sheet, one row per trial in trial order. Anything that goes wrong is logged with its date in ab-test/log.md.
