Flow
- Generate the resume to best match the provided job description
- Once the tex file has been generated, spin up a subagent with the system prompt defined in ATS.md.
  - Pass in the job description and generated resume.tex to the subagent to process
  - The sub agent should return information back.  Use that information to bridge gaps
  - Do this until gaps are closed to a maximum of 3 passesA or if no changes could be made

General Rules
- Always check the final PDF for formatting issues
- When asked to generate the resume, always generate the pdf in addition to the tex file
- Always compile from the **project root** (not from `output/`), so `res.cls` is on the TeX search path:
  pdflatex -output-directory=output output/resume_<identifier>.tex

Apply to the resume as a whole
- Keep the resume under 2 pages
- Optimize for the most recent experience first
- Aim for 15–25 relevant keywords per resume. This range demonstrates expertise without triggering keyword stuffing detection. Keywords should appear because you're describing your real work, not because you're trying to trick the system.
- Try to tie impact to each bullet point under the job description.  Focus on selecting criteria with impact (unless it conflicts heavily with ATS)
- Aim for 75-80% ATS key word match
- Ensure there is a full story for each bullet point, avoid scattered phrases
- Omit any gaps from the resume but surface gaps in the terminal

Apply only to the Career Summary
- Aim to have a 2-3 sentence max
- Avoid mentioning specific technologies

Apply only to the Job Description Summary
- Always include a brief (1-3 sentence) summary per role

Apply only to the Job Description
- Aim to keep the number of bullets per job description to max of 6.  Prioritize the more important ones
- Aim to keep the number of sentences in the bullet points to 2
- Avoid semicolons
- Avoid repetition if possible
- Avoid run on sentences
- Ensure each bullet flows and is relevant.  Each should tell a story
- If certain key concepts are missing that the ATS is probably looking for, weave it in here (ie. I mention microservices, you rephrase to distributed system archiecture).  However ensure that it is grounded in evidence
- Ensure everything flows naturally

Apply only to the Technical Skills
- Aim to keep the number of skills around 10-12.  OK to gover over by 1-2 if we are already missing important ATS key words
- Do not put anything generic or expected in all jobs (ie. RFC, Design docs)
- Aim to keep them as specific technologies or technical archiectural concepts (ie. distributed systems)
- Avoid business level concepts (ie. SLO, SLA)
