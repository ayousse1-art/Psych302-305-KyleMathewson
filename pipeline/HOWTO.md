# PSYCH 302 / 305 Canvas pipeline

Private instructor tool. Token lives in `Psych275_Instructor/pipeline/.env` (same Canvas account). This folder overrides the course id to **35483**.

```bash
cd /Users/kylemathewson/Teaching/PsychCompute302-305/pipeline
source /Users/kylemathewson/Teaching/Psych275_Instructor/pipeline/.venv/bin/activate
python studio_pipeline.py courses
python studio_pipeline.py week0-create
python studio_pipeline.py modules-create
# after students submit:
python studio_pipeline.py week0-pull
python studio_pipeline.py week0-grade          # complete/incomplete from parsed username
python studio_pipeline.py week1-pull           # harvest Week 1 Canvas links; does not grade
python studio_pipeline.py repos-mint           # dry-run plan (default)
python studio_pipeline.py repos-mint --apply   # create private repos + add collaborators
python studio_pipeline.py repos-sync           # dry-run: missing template files on existing repos
python studio_pipeline.py repos-sync --apply   # add missing files only; never overwrite or force-push
python studio_pipeline.py repos-replace --path README.md   # dry-run overwrite listed template files
python studio_pipeline.py repos-replace --path README.md --apply
python studio_pipeline.py modules-create       # Canvas modules + weekly assignment bodies
python studio_pipeline.py assignments-update   # rewrite weekly bodies only; no student email
python studio_pipeline.py assignments-update --from-week 3   # weeks 3+ and Canvas intro/schedule pages
python studio_pipeline.py assignments-update --notify-week 3   # same, email only Week 3
```

`week0-pull` writes `out/week0_roster.json`: Canvas user ↔ GitHub username, Education status, repo consent.

`week0-grade` PUTs Canvas `complete` / `incomplete` only. Complete = parsed GitHub username present and non-empty. Do not invent points. Assignment is `pass_fail` and omitted from the final grade.

`repos-mint` copies the whole `student_template/` tree (root README plus every `weekNN-*/` folder already in the template — currently `week02-rt/`, `week03-inventory/`, `week10-project/`). Per-student copies of a personalized page (for example `week03-inventory/inventory.html` + `inventory.css`) do go in the template; the live handbook page (`rt.html`, `inventory.html`) is the class demo only and is never itself copied. It never copies `pipeline/` or `.env`. Repos are `kylemath/psych302-305-<github_username>`, private. The student is added as a `push` collaborator (write, not admin); kylemath stays owner/admin. Mint only when the username parses **and** `repo_consent=yes`. Default is dry-run. Same-name repos are not overwritten and are never force-pushed.

**Do not** `repos-replace` teaching HTML into student repos. Instruments live on GitHub Pages. Student repos hold that week’s `README.md`, CSV, and any page the student wrote.

`repos-sync` is for repos that already exist. Default is dry-run. `--apply` clones each existing consented repo, copies only files that are still missing, commits, and does a regular `git push`. It never overwrites a file the student already has and never force-pushes. It will not delete leftover `lab-notes/` / `report/` folders from Weeks 0–2.

Instructor demo (Kyle as student): `kylemath/psych302-305-kylemath`, local clone `/Users/kylemathewson/Teaching/psych302-305-kylemath`. Maintain it the same way students maintain theirs.

To the agent: **`plant week0`** means create (or confirm) the assignment and announcement. **`pull week0`** means harvest usernames. **`grade week0`** means complete/incomplete. **`pull week1`** means harvest the four GitHub links from Canvas (do not invent scores). **`mint repos`** means dry-run first, then `--apply` for eligible students only. **`sync repos`** means dry-run first, then `--apply` to add missing template files only.

Students work in **VS Code on their laptops** (GitHub Codespaces is not used). After a handbook push, rewrite Canvas weeklies from Week 3 onward with `assignments-update --from-week 3` (no student email unless `--notify-week`).
