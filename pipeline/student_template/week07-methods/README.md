# Week 7 · Methods: Stroop forward, Hedge backward

**Name:**
**Date of class:** 21 October 2026
**Lab page:** https://kylemath.github.io/Psych302-305-KyleMathewson/methods.html

This folder should end up with: your edited `rt.html` (now a Stroop task),
`stroop-week07.csv`, this README, and `output/numbers.md` from
`analyze_stroop.py`. Individual work.

---

# Part 1 · Forward: Methods first, then the task

Write and commit this Methods **before** you change `rt.html`. Use numbers.

## Participants
Myself completed the Stroop task. This was a self-administered demonstration of the Stroop effect.

## Materials
The experiment was presented in a web browser using an HTML and JavaScript reaction-time task. Four ink colours were used: red, blue, green, and yellow. Participants identified the ink colour by pressing the corresponding key: Z, X, N, or M. The task recorded reaction time, trial condition, response key, and response accuracy.
## Procedure
The experiment began with six practice trials, followed by 20 scored trials. The scored trials consisted of 10 congruent trials, in which the word matched the ink colour, and 10 incongruent trials, in which the word named a different colour. The scored trials were randomly shuffled and presented in a mixed order.

At the beginning of each trial, a fixation cross (+) appeared for a randomly varying interval between 800 and 2,200 ms. A colour word was then displayed in its ink colour and remained visible until a response was made. After each response, there was a 550 ms interval before the next trial began. The participant was instructed to identify the ink colour as quickly and accurately as possible.

## Data handling
Reaction time (RT) was measured in milliseconds from the appearance of the colour word to the participant's response. Responses made before the word appeared were treated as anticipations and excluded from the reaction-time analysis. Responses with RTs below 150 ms or above 2,500 ms were also excluded. Incorrect responses were recorded as errors and excluded from the calculation of mean reaction time. Mean RTs were calculated separately for correct, usable congruent and incongruent trials. The Stroop effect was calculated by subtracting mean congruent RT from mean incongruent RT.

## Decisions I had to invent while coding
I used the Z, X, N, and M keys to represent red, blue, green, and yellow ink, respectively.

I created 20 experimental trials: 10 congruent and 10 incongruent, with trial order shuffled.

I treated responses before the word appeared as anticipations and excluded them from the reaction-time analysis.

I excluded reaction times below 150 ms or above 2,500 ms, and excluded incorrect responses from mean reaction-time calculations.

I calculated the Stroop effect by subtracting mean congruent reaction time from mean incongruent reaction time.

## My result
- Congruent mean RT: 1524 ms.
- Incongruent mean RT: 2022 ms.
- Stroop effect: 498 ms (2022 − 1524).
- Usable correct trials: 18 out of 20.

---

# Part 2 · Backward: from Hedge's result to Hedge's Methods

Hedge, C., Powell, G., & Sumner, P. (2018). The reliability paradox: Why
robust cognitive tasks do not produce reliable individual differences.
*Behavior Research Methods, 50*(3), 1166–1186.
https://doi.org/10.3758/s13428-017-0935-1

## My guess (write before opening their Methods)
I predicted that the study would recruit undergraduate students and have them complete a computerized Stroop task in which they identified the ink colour of colour words. I expected participants to use keys corresponding to red, blue, green, and yellow, with congruent trials (word and ink match) and incongruent trials (word and ink differ) presented in randomized order. I expected the researchers to calculate the Stroop effect by subtracting mean congruent reaction time from mean incongruent reaction time. I was unsure how many trials participants completed, whether the study included neutral trials, how long participants waited between sessions, and the exact criteria used to exclude participants and reaction times.

## What I missed
1. **The number and types of trials:** I did not anticipate that participants completed 240 trials in each of three conditions—congruent, incongruent, and neutral—for 720 trials total. The neutral condition used the words “lot,” “ship,” “cross,” and “advice.” This matters because neutral trials provide an additional comparison condition, and using only congruent and incongruent trials changes the task design.

2. **The session structure and timing:** I did not anticipate that participants completed two 90-minute sessions approximately three weeks apart, at the same time of day. The word remained on screen until a response, and trials had a 750 ms inter-stimulus interval. These details matter because practice, fatigue, timing, and the interval between sessions can influence reaction times and estimates of test-retest reliability.

3. **The exclusion rules:** I did not anticipate the exact reaction-time exclusion rule: responses under 100 ms or more than three median absolute deviations from an individual's median were excluded. Participants were also excluded from a task if accuracy fell below 60% in either session or if they did not return for follow-up. These criteria differ from my task's 150–2500 ms limits and show that exclusion decisions can change which observations contribute to the mean reaction times and Stroop effect.

## Reanalysis
Rule: `hedge`. Participants: 105 kept, 2 excluded (missing a session or accuracy under 60%).

| Session | Congruent (ms) | Incongruent (ms) | Stroop effect (ms) | Effect > 0 |
| --- | --- | --- | --- | --- |
| 1 | 593 | 672 | 80 (SD 43) | 105 of 105 |
| 2 | 571 | 630 | 59 (SD 36) | 105 of 105 |

Session 1 vs session 2, same people three weeks apart (Pearson r):
- Stroop effect: r = 0.72
- Plain congruent RT: r = 0.77

The paper reports ICCs, not Pearson r, so expect close but not identical numbers.

Me (`stroop-week07.csv`, 18 usable correct trials): congruent 1524 ms, incongruent 2022 ms, Stroop effect 498 ms. That is larger than 105 of 105 Hedge participants in session 1.

- Is the group Stroop effect robust?
  - Yes. Under the Hedge rule, all 105 participants had a positive Stroop effect in both sessions. Under the course rule, all 105 had a positive effect in session 1 and 104 of 105 in session 2. The group effect remained positive under both rules, although the averages changed.

- Is a person's Stroop effect stable from session 1 to session 2?
  - The Pearson correlation was r = 0.72 under the Hedge rule and r = 0.65 under the course rule. Both suggest some stability in individual differences across sessions, but the estimates depend on the exclusion rule.

- Run it again with `--rule course`. What changed, and what does that say about writing exclusion rules in a Methods section?
  - My usable correct trials decreased from 18 to 15. My congruent mean RT changed from 1524 to 1232 ms, my incongruent mean RT changed from 2022 to 1924 ms, and my Stroop effect increased from 498 to 693 ms. The group session 1 effect changed from 80 to 84 ms, and the session 2 effect changed from 59 to 63 ms. This demonstrates that exclusion rules can affect results, so researchers must define and report them clearly and consistently.

---

## Copilot / agent disclosure
- **Used tonight:** yes 
- **What I asked** (one sentence):I asked ChatGPT for help troubleshooting my CSV file, running the Stroop analysis, interpreting the output, and drafting sections of my report.
- **What I kept:** I kept the guidance that helped me run the experiment, analyze my data, and understand the exclusion-rule comparison.
- **What I changed:** I checked the analysis output and edited the report to reflect my own experiment and understanding.

If no assistant was available, write “no Copilot tonight” and stop. Do not purchase a plan.