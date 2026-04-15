# Generic Guidelines for generation
- Always check the final PDF for formatting issues
- When asked to generate the resume, always generate the pdf in addition to the tex file
- Always compile from the **project root** (not from `output/`), so `res.cls` is on the TeX search path:
  pdflatex -output-directory=output output/resume_<identifier>.tex

# Guidelines for resume content
- Keep the resume under 2 pages
- Optimize for the most recent experience first
- Aim for 15–25 relevant keywords per resume. This range demonstrates expertise without triggering keyword stuffing detection. Keywords should appear because you're describing your real work, not because you're trying to trick the system.
- Try to tie impact to each bullet point under the job description.  Focus on selecting criteria with impact (unless it conflicts heavily with ATS)
- Aim for 75-80% ATS key word match
- Ensure there is a full story for each bullet point, avoid scattered phrases
- Omit any gaps from the resume but surface gaps in the terminal
- Aim to keep the number of bullets per job description to max of 6.  Prioritize the more important ones
- Aim to keep the number of sentences in the bullet points to 2
- Avoid semi colons
- Avoid repetition if possible
- Avoid run on sentences
- Always include a brief (1-3 sentence) summary per role
