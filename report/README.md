# Research report pipeline

Week 4 laboratory. Keep this folder in the private studio repository.

The loop is: edit prose or the script → run the script → read the generated numbers → change something → run again. Do not type a mean by hand.

```
report/
  REPORT.md              # the markdown paper you write
  main.tex               # the same paper in LaTeX
  scripts/summarize.py   # reads a CSV, writes numbers
  output/numbers.md      # generated; do not edit
  output/numbers.tex     # generated; do not edit
  build.sh               # one command for the loop
```

## Run once

Copy these files into `week04-report/` in your private repository, put your
CSV in that same folder (or point at an earlier week’s folder, for example
`../week02-rt/` or `../week03-inventory/`), then from `week04-report/` in the
VS Code terminal:

```bash
python3 -m venv .venv
source .venv/bin/activate
python scripts/summarize.py --csv YOURFILE.csv
bash build.sh YOURFILE.csv
```

Windows (VS Code PowerShell):

```powershell
py -3 -m venv .venv
.\.venv\Scripts\Activate.ps1
py -3 scripts/summarize.py --csv YOURFILE.csv --out output --report REPORT.md
```

If Git for Windows is installed, `bash build.sh YOURFILE.csv` also works.

`summarize.py` uses only the Python standard library. The virtual environment is so later packages (if you add any) stay off the system Python. Do not `pip install` unless the instructor says to.

If `pdflatex` is missing, that is fine tonight. The graded files are `REPORT.md`, `main.tex`, the script, and the generated snippets. A PDF is a bonus, not a requirement.

## The loop

1. Write a prediction in `REPORT.md` *before* you look at the generated mean.
2. Run the script.
3. Read `output/numbers.md`. If the n or the mean looks wrong, fix the CSV path or the exclusion rule in the script — do not edit `output/`.
4. Change one sentence of prose, or one line of the script.
5. Run again. Note what changed.

Keep the week-4 files in `week04-report/` (the report is that folder’s `README.md`; you may also keep `REPORT.md` as the long paper). Do not copy a second note into `lab-notes/`.
