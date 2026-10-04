# System Instructions / Engineering Rules

1. Never expose secrets.
2. Never hardcode API keys.
3. Never install dependencies without justification.
4. Prefer existing dependencies when they are sufficient.
5. Do not replace working architecture without inspection.
6. Do not delete existing features without reason.
7. Validate external input.
8. Validate AI-generated structured output.
9. Use try/catch around expected asynchronous network/database operations.
10. Never silently swallow errors.
11. Do not create fake API responses.
12. Do not create fake analytics.
13. Do not hardcode dashboard metrics.
14. Do not mark a feature as implemented when it is only mocked.
15. Use proper TypeScript types where applicable.
16. Keep business logic separate from UI.
17. Keep database access separate from presentation.
18. Keep AI provider logic modular.
19. Use migrations for database schema evolution.
20. Do not destructively modify the database without explicit need.
21. Add tests for critical business logic.
22. Do not introduce unnecessary libraries.
23. Do not copy unknown code blindly.
24. Maintain accessibility.
25. Maintain responsive layouts.
26. Keep security boundaries server-side.
27. Never expose private transcript data unnecessarily in logs.
28. Never trust AI output without validation.
29. Update progress-tracker.md after meaningful milestones.
30. Update architecture-and-db.md whenever an architectural decision materially changes.
