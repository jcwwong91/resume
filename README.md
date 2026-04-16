# To Any Recuiters or Hiring Managers

This project contains a comprehensive overview of major accomplishments I have made overtime, feel free to take a look if you want to understand my experience in greater detail!  Always happy to talk more about my experience and thanks for stopping by!

# Resume Generator

This project generates custom-tailored resumes from a structured knowledge base of professional experience. Each resume is optimized for a specific job description using an AI-assisted workflow.

## How It Works

1. Provide a job description to Claude Code.
2. Claude reads your experience sources and generates a tailored `.tex` file under `output/`.
3. The `.tex` file is compiled to PDF using `pdflatex`.

## Project Structure

```
.
├── resume.tex              # Master resume template (never edited directly)
├── projects.md             # Source of truth for all project bullets
├── guidelines.md           # Formatting and content rules for resume generation
├── personal.tex            # PII (gitignored) — name, address, phone, email
├── jobs/
│   ├── linkedin.md         # Skills and experience evidence from LinkedIn
│   └── continental.md      # Skills and experience evidence from Continental
└── output/
    └── resume_<id>.tex/.pdf  # Generated resumes, one per target role
```

## Generating a Resume

Open Claude Code in this directory and paste in a job description:

```
Generate a resume optimized for this JD

<paste job description here>
```

Claude will produce `output/resume_<identifier>.tex` and compile it to PDF. Any gaps between the JD and your documented experience will be surfaced in the terminal.

## Adding Experience

- **New project:** Add an entry to `projects.md` following the existing format. Include a "What it was NOT" section to prevent overreach.
- **New skill:** Add evidence under the relevant skill heading in `jobs/<employer>.md`.
- **New employer:** Create a new file under `jobs/` following the existing format.

## Compilation

Compile from the **project root** (not from `output/`) so `res.cls` is on the TeX search path:

```bash
pdflatex -output-directory=output output/resume_<identifier>.tex
```
