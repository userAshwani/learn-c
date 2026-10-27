# Repo rules

- Never run `git add`, `git commit`, or `git push`, and never stage files.
- After finishing any task, always end the response with a suggested
  commit message in a fenced code block, written in imperative mood
  (e.g. "Add note on pointer arithmetic"), so the user can review, commit,
  and push themselves.

## Turning screenshots into notes

The user will often paste or attach screenshots of content they're
learning from (a course, article, video, book, etc.) and expect a finished
note created from it with no further back-and-forth. When that happens:

1. Read the screenshot(s) and identify the underlying topic and whether
   it's a concept or a practice problem.
2. Pick the right existing numbered topic folder
   (`01-getting-started/`, `02-basics/`, `03-control-flow/`,
   `04-functions/`, `05-pointers-and-memory/`, `06-arrays-and-strings/`,
   `07-structs-and-unions/`, `08-file-io/`, `09-problems/` for practice
   problems). If none of these genuinely fit, create a new folder
   following the same `NN-topic-name/` numbering convention, placed in
   sensible learning order — don't force content into the wrong folder.
3. Create the `.md` file (kebab-case filename) and write the frontmatter
   contract exactly as documented in README.md.
4. Write the note content in the user's own voice — explain it like
   teaching someone else, don't transcribe or lightly reword the
   screenshot. For `09-problems/` entries, follow that section's
   structure: problem statement in own words, approach/reasoning, the
   solution, then time/space complexity.
5. Use fenced ` ```c ` blocks for reference snippets and ` ```c run ` only
   for short, self-contained runnable examples, per README.md.
6. Do this automatically — don't ask the user to confirm the folder,
   filename, or frontmatter values first. If a screenshot is genuinely
   ambiguous (e.g. it could belong in two very different topics, or isn't
   C-related at all), ask; otherwise just create the note.
7. Still follow the git rule above: never stage or commit, just end the
   response with a suggested commit message.
