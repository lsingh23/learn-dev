# React UI Machine Coding — Guide Roadmap

Series lives at `34-*.html` onwards. Goal of this series is **not** deep React theory.
It is: *given a UI prompt in a 45-minute interview, how do you reason your way to a
working thing?* Framework before house. Simplest solution first, then specifics.

Every guide in this series must:
- be short (aim ~1200–1800 words, far shorter than guides 01–33)
- lead with the **state shape**, not the JSX
- give a repeatable 5-step build order
- show the simplest version that works, then one or two upgrades
- end with a compact "what the interviewer is actually checking" list
- reuse the `<style>` block from `28-implement-debounce-and-throttle.html` verbatim

## Status

| # | File | Topics covered | Status |
|---|------|----------------|--------|
| 34 | `34-ui-the-interview-framework.html` | The meta-method: decompose → state shape → static render → wire events → polish | ✅ |
| 35 | `35-ui-star-rating-accordion-tabs.html` | 2. Star rating · 3. Accordion · 4. Tabs | ✅ |
| 36 | `36-ui-modal-toast-traffic-light.html` | 5. Modal · 19. Toast system · 9. Traffic light | ✅ |
| 37 | `37-ui-debounced-search-and-custom-hooks.html` | 1. Debounced search/autocomplete · 10. useDebounce, useLocalStorage | ✅ |
| 38 | `38-ui-pagination-and-sortable-table.html` | 6. Pagination / data table · 24. Sortable table | ✅ |
| 39 | `39-ui-timer-counter-progress.html` | 7. Timer / stopwatch / counter · 8. Progress bar | ✅ |
| 40 | `40-ui-async-lists-usefetch-infinite-scroll.html` | 22. Job board list states · 23. useFetch + abort · 11. Infinite scroll | ✅ |
| 41 | `41-ui-recursive-trees-and-nested-checkboxes.html` | 13. Nested comments / file explorer · 17. Nested checkboxes | ✅ |
| 42 | `42-ui-cart-and-optimistic-updates.html` | 14. Shopping cart · 25. Like button / optimistic toggle | ✅ |
| 43 | `43-ui-forms-validation-and-wizard.html` | 21. Contact form · 15. Multi-step wizard | ✅ |
| 44 | `44-ui-carousel-and-otp-input.html` | 16. Image carousel · 18. OTP input | ✅ |
| 45 | `45-ui-tic-tac-toe.html` | 20. Tic-tac-toe (+ grid-game generalisation) | ✅ |

## Original topic list (source of truth for coverage)

1. Debounced search / autocomplete → 37
2. Star rating → 35
3. Accordion → 35
4. Tabs → 35
5. Modal → 36
6. Pagination / data table → 38
7. Timer / stopwatch / counter → 39
8. Progress bar → 39
9. Traffic light → 36
10. Custom hooks — useDebounce, useLocalStorage → 37
11. Infinite scroll → 40
13. Nested comments / file explorer (recursive tree) → 41
14. Shopping cart — add, remove, quantity, total → 42
15. Multi-step form wizard with validation → 43
16. Image carousel → 44
17. Nested checkboxes — parent/child selection → 41
18. OTP input — auto-focus, backspace, paste → 44
19. Toast / notification system with auto-dismiss → 36
20. Tic-tac-toe → 45
21. Contact form — controlled inputs + validation → 43
22. Job board / API list with loading + error states → 40
23. useFetch custom hook — with cleanup and abort → 40
24. Sortable table — click header to sort → 38
25. Like button / toggle with optimistic update → 42

## Ideas for a future batch
Drag & drop list reorder · Kanban board · Calendar / date picker · Virtualised list ·
Command palette (⌘K) · Chess/Minesweeper board · Undo/redo · Poll widget · Type-ahead with
keyboard nav · Comment editor with mentions
