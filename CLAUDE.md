# Resume Project — Claude Context

The goal of this project is to generate a custom tailored resume based on what I have done professionally.

# Sources
- 'guidelines.md` contains general rules for resume optimization
- `projects.md` — all projects I have worked on; contains "What it was NOT" sections — treat as ground truth for all project bullets
- `/jobs/*.md` — one file per employer (e.g. `linkedin.md`, `continental.md`); contains demonstrated skills and experience; required evidence before listing any skill
- `personal.tex` contains PII that you don't need to worry about.  Ignore this file and only use it for latex compilation
- `resume.tex` contains the actual resume format

## Rules

1. **Never embellish.** All bullets must be supportable by `projects.md`. When in doubt, omit or ask.
2. **Never modify `resume.tex`.** Create a new file for every tailored version. (output/resume_(identifier).tex)
3. **Scope claims accurately.** State what was specifically owned — not what the broader team delivered.
4. **Check `projects.md` before writing project bullets.** It contains "What it was NOT" sections to prevent overreach.
5. **Check `jobs/*.md` for skill evidence.** Only list a skill if evidence exists there.
6. **If detail is missing from reference files, ask — do not infer.**
7. **Always ask for confirmation before modifying any `*.md` file.**
8. **Always follow `resume.tex` format.  Do not omit anything besides placeholder items
