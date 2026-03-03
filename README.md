# ITS Database Reviewer

A simple single-page web application designed as a study tool for database concepts, originally created for
University of Mindanao students. The entire project lives in a standalone HTML file (`its_database_reviewer originl.html`),
which contains markup, styles, and a large JavaScript quiz engine.

## Features

- **40-question random quiz** drawn from a set of 200 database and SQL questions.
- **Single‑choice and multiple‑choice** questions with immediate feedback.
- **Score tracking** including correct, wrong, and unanswered counts.
- **Filtering** by answered state (all, unanswered, correct, wrong).
- **Search box** to find questions or choices by keyword.
- **Progress bar** and statistics bar for visual cues.
- **Submit all** button to grade and show results in a popup window with percentage and grade.
- **New random set** button to reshuffle a different subset of questions.
- **Expandable/collapsible** question cards for easier navigation.
- **Scroll-to-top** button, type badges, and responsive styling.

## Code Organization

All logic is embedded within the HTML file, which includes:

1. **CSS** – custom dark theme variables, layout, and component styles defined in a `<style>` block.
2. **JavaScript** – an array of question objects (`ALL_QUESTIONS`) with fields such as `id`, `text`, `choices`,
   `answer`, and `expl` (explanation). Helper functions handle rendering, state management, filtering, searching,
   and scoring.
3. **HTML** – markup for the header, controls, statistics, filters, search box, progress bar, question container,
   result popup, and scroll button.

Since everything is contained in one file, the repository currently only consists of the HTML file and this README.

## Editing Questions

To update the question set, open the HTML file and locate the `ALL_QUESTIONS` array near the top of the
`<script>` section. Each entry follows this structure:

```js
{
  id: 1,
  text: "Question text...",
  type: "single" | "multi",
  choices: ["Option A","Option B", ...],
  answer: [index, ...], // zero-based indexes of correct choices
  expl: "<strong>Explanation</strong> text..."
}
```

- Use `type: "multi"` when more than one answer is allowed; otherwise use `"single"`.
- The `answer` array may contain multiple indexes for multi‑select questions.
- Explanation HTML is displayed after a question is submitted.

## Usage

Simply open `its_database_reviewer originl.html` in any modern web browser. No server or build steps are required.

## Future Enhancements

- Extract JavaScript and CSS into separate files for maintainability.
- Add persistent storage (localStorage) to save progress between sessions.
- Generate printable or exportable reports.
- Provide an admin interface to add/edit questions via a form.

## License

This project is intended as an educational resource and may be freely used and modified.

---

*Created by ITS Database Reviewer team.*
