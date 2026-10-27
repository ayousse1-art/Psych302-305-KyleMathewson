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
Every choice the code forced on you that your Methods above did not answer.
One line each. (Then go back and add them to the Methods.)

## My result
Congruent mean RT, incongruent mean RT, Stroop effect (ms), number of errors.
CSV columns must include `condition`, `rt`, and `correct`.

---

# Part 2 · Backward: from Hedge's result to Hedge's Methods

Hedge, C., Powell, G., & Sumner, P. (2018). The reliability paradox: Why
robust cognitive tasks do not produce reliable individual differences.
*Behavior Research Methods, 50*(3), 1166–1186.
https://doi.org/10.3758/s13428-017-0935-1

## My guess (write before opening their Methods)
From the abstract and result alone: who, how many, what the task looked like,
how many trials, how long between sessions, which trials were thrown out.

## What I missed
After reading their Stroop Methods: three details you got wrong or did not
think of, and whether each one could change the result.

## Reanalysis
Run `python3 analyze_stroop.py --mine stroop-week07.csv` and paste
`output/numbers.md` here. Then one sentence each:
- Is the group Stroop effect robust?
- Is a person's Stroop effect stable from session 1 to session 2?
- Run it again with `--rule course`. What changed, and what does that say about
  writing exclusion rules in a Methods section?

---

## Copilot / agent disclosure
- **Used tonight:** yes / no
- **What I asked** (one sentence):
- **What I kept:**
- **What I changed:**

If no assistant was available, write “no Copilot tonight” and stop. Do not purchase a plan.