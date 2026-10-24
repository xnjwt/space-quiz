# Copilot instructions

## Project shape

Órbita is a dependency-free, static Spanish-language space quiz. The entire application lives in `index.html`: semantic page markup, light/dark theme styles, animation and responsive rules, the question bank, and quiz behavior are all inline. There is no build pipeline or separate application layer; open the file directly in a browser.

The `questions` array is the source of quiz content. Each item has a `question`, four `answers`, a zero-based `correct` answer index, and an `explanation`. `renderQuestion()` builds the options and updates progress, `selectAnswer()` handles scoring and feedback, `showResults()` chooses the end-of-quiz reaction, and `restartQuiz()` reconstructs the initial quiz markup. Keep the initial markup and the markup recreated by `restartQuiz()` in sync when changing the quiz UI.

## Build, test, and lint

There are no configured build, test, or lint commands. No package manifest or test runner is present. Run the app by opening `index.html` directly in a browser; there is no server or installation step.

For a manual browser smoke test, verify answer selection and keyboard focus, score increments only for correct answers, correct/incorrect feedback, progress through all ten questions, the final score/reaction, and restart. Also check the light/dark system themes and reduced-motion behavior when changing styles or animations. There is no separate single-test command.

## Code conventions

- Keep the app self-contained and dependency-free; quiz content, styles, and behavior belong in `index.html`.
- User-facing copy is Spanish. Preserve the existing Spanish labels, explanations, and space-exploration tone.
- Theme colors are CSS custom properties in `:root`, with dark-mode overrides under `@media (prefers-color-scheme: dark)`. Use these tokens for new UI states so both themes remain coherent.
- Preserve semantic controls and accessibility: answer choices and actions are native buttons, feedback uses a live status region, progress exposes its value through ARIA, keyboard focus is deliberately moved between questions/results, and decorative effects are hidden from assistive technology.
- Honor `prefers-reduced-motion`: keep motion optional and avoid launching confetti when the preference is enabled.
- Build answer text from the question data with `textContent`; keep the correct answer index zero-based and explanations attached to their question.
