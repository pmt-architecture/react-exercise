# Introduction

This repository is a base for an exercise where we want candidates to demonstrate their technical skills.

Clone the repo and execute the exercise. In the end, share the code with us via your own personal repo.

# Getting started

```bash
pnpm install
pnpm run mock   # starts the mock api at http://localhost:3001
pnpm run dev    # starts the app (use a second terminal)
```

# The challenge — Credit Simulator

**Timebox: ~1 hour.** The exercise is scoped to fit in one hour — prioritize working functionality over visual polish. We do **not** evaluate pixel-perfect design.

- Goal:

   Build a **single-screen credit simulator** where the client chooses an amount and a repayment period, and instantly sees the estimated monthly payment.

- Requirements:

   1. **Limits (API):** on load, fetch the credit limits from the mock api (`GET http://localhost:3001/limits` → `{ min, max, currency }`). Show a loading state while fetching. The limits must be visible on screen.
   2. **Amount:** a text input **and** a slider, kept in sync — changing one updates the other. The value is bounded by the limits from the api; an out-of-range value must show a validation message.
   3. **Months:** the user selects the number of months to pay, from **3 to 12**. Use the component you prefer (select, radio group, buttons…) — no slider needed here.
   4. **Monthly payment (live):** show the estimated monthly payment, recalculated as the user changes amount or months. Keep the math intentionally simple — we are not evaluating finance formulas:

      `monthly = (amount * 1.05) / months` (flat 5% fee)

   5. **Formatting:** display money values formatted as currency, using the `currency` returned by the api.

- Bonus (only if you have time left — **not required**):

   - Persist the last simulation in `localStorage` and restore it on reload
   - A unit test for the monthly payment calculation
   - Any UX nicety you find relevant (debounce, keyboard support, …)

- What we look at:

   - Component structure and separation of concerns
   - Hooks and state management (including derived state)
   - TypeScript usage
   - Handling of async data (loading / error states)
   - Controlled inputs and validation

- Tech notes:
   - The repository already has shadcn/ui configured, so if you have experience with it, go ahead; otherwise use a component lib of your choice in a way you are comfortable, to reduce time spent on investigation or technical details
   - Use TypeScript
   - The api mock is already in place — just run `pnpm run mock`. The endpoint is at http://localhost:3001/limits
