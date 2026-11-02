# A/B Test Plan, Free Hot Yoga Page

MKTG:4400 Digital Marketing, Project Deliverable 3. Hanna Van Camp. Written and committed November 2, 2026, before any data was collected.

## Page and element

The test runs on the free classes page (try-it-free.html), which targets "free hot yoga" queries. The single element being changed is the opening paragraph under the H1. Everything else on the page stays identical.

**Version A (current page, try-it-free.html)** opens with the cost problem.

> A monthly membership is a lot to spend on something you have never tried. The good news is that every studio in the area wants new students, so there are several ways to take your first few classes for free or close to it.

**Version B (try-it-free-b.html)** opens with the concrete offer.

> Your first hot yoga class in Iowa City can be completely free. Riverbend Heat Studio covers your first intro class, and the other two studios offer unlimited intro weeks for $25 and $30, so you can try heated yoga before you spend anything on a membership.

The two paragraphs are close in length (44 and 46 words). Version B carries a noindex tag and a canonical tag pointing to version A, and it is left out of sitemap.xml, so it does not compete with version A in search.

## Hypothesis

Visitors shown version B will rate themselves more likely to book a free or intro class than visitors shown version A.

The reasoning is that someone searching for free hot yoga has already decided cost is the barrier. Version A spends its opening restating that barrier and only promises that deals exist, while version B answers the question in the first sentence with a specific free class and specific prices. Putting the answer first should make the offer feel more real and lower the effort of acting on it. This prediction could be wrong. Version A's framing may feel more empathetic to a hesitant beginner, and the rest of the page already lists every offer, so the opening paragraph may not matter at all.

## Visitors, prompt, and assignment

**Model.** Claude Sonnet 5.5 (model ID claude-sonnet-5-5) with default settings. The same model and settings are used for every trial.

**Fresh conversation.** Each trial runs in its own new session with no memory of any earlier trial.

**Page shown.** The full visible text of the page (notice, header, navigation, hero, main content, and footer), extracted the same way for both versions. The only difference between the two page texts is the opening paragraph.

**Exact prompt, identical in every trial except for the page text.**

> You are a University of Iowa student who has never tried hot yoga. You are curious about it but on a tight budget, and you just searched Google for "free hot yoga iowa city" and clicked on this page. Read the page below and decide how likely you are to book a free or intro class at one of the studios it describes.
>
> Answer on the first line with a single number from 1 to 7, where 1 means "definitely would not book" and 7 means "definitely would book." On the second line, give one sentence explaining your rating.
>
> PAGE:
> [full page text of version A or version B]

**Assignment.** The order of versions was generated before any trial with Python's random module (seed 20261110), shuffling exactly 50 A and 50 B assignments. The list is committed alongside this plan as ab-test/assignments.csv, and trial N is run with the version listed in row N.

## Primary outcome

The 1 to 7 rating on the first line of each response. A response that does not begin with a whole number from 1 to 7 is logged as invalid, kept in the raw data, and reported, not dropped silently.

## Sample size and timing

100 trials total, 50 per version. Data collection starts no later than Tuesday, November 10, 2026, and all 100 trials will be complete by Saturday, November 14, 2026. I will not look at results until all 100 trials are finished, and I will not stop early.

## Comparison and what counts as support

The comparison is the mean rating in version B minus the mean rating in version A, tested with a two-sided Welch two-sample t-test at a significance level of 0.05. As a check on the skewed 1 to 7 scale, I will also report a Mann-Whitney U test, but the t-test is the primary result.

The hypothesis is supported if version B's mean is higher than version A's and the t-test p-value is below 0.05. A difference in the other direction, or a p-value of 0.05 or above, means the test does not support the hypothesis, and I will report that as the result.

## Records kept

Every prompt, response, model version, and trial date goes into ab-test/results.csv (one row per trial), with any problems logged in ab-test/log.md with dates.
