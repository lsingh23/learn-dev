# Frontend Interview — Conceptual Question Bank (by Importance)

Distilled from GreatFrontEnd, BFE.dev, curated "Top N" lists, and aggregated interview-experience write-ups.
Conceptual/theory only — coding/machine-coding questions excluded on purpose.
Tiers: **T1** = asked in nearly every interview · **T2** = common follow-up / mid-frequency · **T3** = occasional, senior-leaning, or JD-specific.

---

## 1. JavaScript Core

**T1**
- Closures (what/why/use cases)
- `var` vs `let` vs `const`, hoisting, temporal dead zone
- `this` binding rules + `call`/`apply`/`bind`
- Event loop: call stack, macrotask vs microtask queue
- Promises: states, chaining, `async`/`await`, error handling
- `==` vs `===`, type coercion
- Prototypal inheritance / prototype chain
- Event bubbling vs capturing, event delegation

**T2**
- Lexical scope, block vs function scope
- `Promise.all` vs `allSettled` vs `race` vs `any`
- Debounce vs throttle (concept/difference)
- Shallow vs deep copy, mutability
- `null` vs `undefined`
- Higher-order functions, currying (concept)
- ESM vs CommonJS, import/export semantics
- `map`/`filter`/`reduce` — when to use which
- Memory leaks / garbage collection basics
- `localStorage` vs `sessionStorage` vs cookies

**T3**
- Generators, iterators, `Symbol`
- `WeakMap` / `WeakSet` — why they exist
- Currying vs partial application
- Proxies / Reflect, tagged templates
- Web Workers / Service Workers basics
- Same-origin policy (see also Security section)

---

## 2. React Core

**T1**
- Virtual DOM + reconciliation (diffing, high level)
- `useState` vs `useEffect` — dependency array pitfalls, stale closures
- Controlled vs uncontrolled components
- Keys in lists — why, and why not array index
- Props vs state
- Class lifecycle methods mapped to hooks

**T2**
- `useMemo` vs `useCallback` vs `React.memo` — when they actually help
- Context API vs prop drilling vs external store (when to reach for each)
- `useEffect` vs `useLayoutEffect`
- Custom hooks, rules of hooks
- Unidirectional data flow / lifting state up
- React 18 automatic batching
- Server components vs client components

**T3**
- Fiber architecture (why React rewrote its reconciler)
- Concurrent features: `useTransition`, `useDeferredValue`, Suspense
- Error boundaries
- Portals
- Render props / HOC patterns (legacy but still asked)

---

## 3. State & Data Management (Redux / Zustand / Context / React Query / SWR)

**T1**
- Why global state exists — problem prop drilling / Context solve vs don't solve
- Redux core concepts: store, actions, reducers, unidirectional flow
- When Context API is enough vs when you need Redux/Zustand
- Client state vs server state — why they're treated differently (this distinction is *the* framing question for React Query/SWR)

**T2**
- Redux Toolkit vs "classic" Redux (why RTK exists — boilerplate reduction)
- Zustand vs Redux — API simplicity, no boilerplate, minimal re-renders
- React Query / TanStack Query: `staleTime` vs `gcTime` (cache lifetime concepts), background refetching, query invalidation
- Stale-while-revalidate concept (SWR's namesake strategy)
- Why you shouldn't put server data in Redux/Zustand (cache sync problem)
- Optimistic updates (concept)
- Redux middleware concept (thunk/saga — what problem middleware solves)

**T3**
- RTK Query vs TanStack Query vs SWR tradeoffs
- Selector memoization / re-render optimization in Redux (`reselect`)
- Normalizing state shape (entity adapters)
- Recoil/Jotai/Valtio — atomic state model (only if JD mentions them)

---

## 4. TypeScript

**T1**
- `interface` vs `type` — differences, when to use which
- `any` vs `unknown`
- Generics — why/what problem they solve
- Structural typing (duck typing) vs nominal typing

**T2**
- Utility types: `Partial`, `Pick`, `Omit`, `Record`, etc. (concept, not memorization)
- Union vs intersection types
- Type narrowing / type guards
- Optional chaining `?.` and nullish coalescing `??`
- How TypeScript integrates with React (typing props, hooks, events)

**T3**
- Declaration merging
- Mapped types / conditional types
- `enum` vs union of string literals (why seniors avoid `enum`)
- Using the type system to model app/product states (senior framing)

---

## 5. Tooling & Build

**T1**
- `package.json` vs `package-lock.json` (deterministic installs, semver ranges vs pinned versions)
- What a module bundler does and why you need one
- Tree shaking (dead code elimination, needs ESM)
- Code splitting / dynamic `import()`
- Webpack vs Vite — bundle-then-serve vs native-ESM-dev-server conceptual difference

**T2**
- Loaders vs plugins (Webpack vocabulary)
- `dependencies` vs `devDependencies` vs `peerDependencies`
- Semantic versioning (`^`, `~`, exact pins)
- Why lockfiles are committed to git
- Babel/transpilation — what it does vs what bundlers do
- Source maps
- Build-time vs runtime environment variables

**T3**
- Monorepo tooling (Turborepo, Nx, workspaces)
- npm vs yarn vs pnpm (pnpm's content-addressable store pitch)
- HMR internals
- Module federation / micro-frontends
- esbuild / SWC / Turbopack — why the shift to Rust/Go tooling

---

## 6. CSS

**T1**
- Box model (`content-box` vs `border-box`)
- Flexbox vs Grid — 1D vs 2D, when to use which
- CSS specificity (inline > ID > class/attr/pseudo-class > element) + cascade
- Positioning (`static`/`relative`/`absolute`/`fixed`/`sticky`)

**T2**
- Stacking contexts / `z-index` (only applies to positioned + flex/grid children)
- Responsive design: media queries, mobile-first
- Units: `px` vs `em` vs `rem` vs `%` vs viewport units
- CSS custom properties (variables)
- Centering techniques (the classic "center a div" — conceptual, not code)

**T3**
- BEM / CSS methodology, CSS-in-JS vs utility-first (Tailwind) tradeoffs
- Layout algorithms (why Grid enables holy-grail layouts)
- Animation performance (`transform`/`opacity` vs layout-triggering properties)

---

## 7. HTML & Accessibility (a11y)

**T1**
- Semantic HTML — why, and difference between `<div>`/`<section>`/`<article>`
- ARIA — when to use it (only when native HTML can't do the job)
- Keyboard navigation / focus management basics

**T2**
- Screen reader interaction model (how semantics get announced)
- Color contrast requirements
- Form accessibility (`label` association, error announcements)
- Landmark roles, document outline

**T3**
- WCAG levels (A/AA/AAA) — general awareness
- Focus trapping in modals
- Live regions (`aria-live`)

---

## 8. Web Performance

**T1**
- Core Web Vitals: LCP, INP, CLS — what each measures
- Critical rendering path (DOM → CSSOM → render tree → layout → paint)
- Lazy loading (and why not to lazy-load the LCP image)

**T2**
- Code splitting / bundle size reduction strategies
- Image optimization (formats, responsive images)
- Render-blocking resources — how to eliminate
- Debouncing/throttling as a performance technique (cross-ref JS section)
- Caching strategies (browser cache, HTTP caching headers — concept)

**T3**
- Virtualization for long lists
- Diagnosing perf issues with DevTools (profiler, flame charts) — walk-through framing
- Prefetch/preload/preconnect resource hints
- Main-thread work reduction, web workers for offloading

---

## 9. Testing

**T1**
- Unit vs integration vs E2E — what each covers, isolation vs realism tradeoff
- What makes a test brittle (implementation detail testing vs behavior testing)

**T2**
- Mocking (when/why, risk of over-mocking)
- Testing async UI (loading/error/success states)
- Snapshot testing — pros/cons, why they get flaky
- Given a bug ("why did checkout break?"), what would you test before merging

**T3**
- Test pyramid concept (why fewer E2E, more unit)
- Visual regression testing
- Contract testing (for API-consuming frontends)

---

## 10. Security & Networking

**T1**
- XSS (stored/reflected/DOM-based) — what it is, how to prevent (sanitization, avoid raw `innerHTML`/`dangerouslySetInnerHTML`)
- CORS — same-origin policy, why the browser blocks cross-origin reads by default
- CSRF — what it is, prevention (SameSite cookies, CSRF tokens)

**T2**
- Content Security Policy (CSP) — what it restricts
- HTTP caching headers (concept: `Cache-Control`, ETags)
- Cookies: `HttpOnly`, `Secure`, `SameSite` attributes
- Where to store auth tokens (cookie vs localStorage tradeoffs)

**T3**
- HTTPS/TLS basics (why it matters for frontend, not just backend)
- Subresource Integrity (SRI)
- Clickjacking / `X-Frame-Options`

---

## 11. Frontend System Design

**T1**
- RADIO framework: Requirements → Architecture → Data model → Interface → Optimizations
- Component API design (props, composition over configuration)
- Local vs global state decision-making in a larger app

**T2**
- Classic prompts: autocomplete/typeahead, infinite scroll photo gallery, news feed, multi-step form, video player
- Data fetching & caching strategy at the app level
- Real-time updates: polling vs WebSockets vs SSE
- Error/loading state handling patterns across an app

**T3**
- Design systems (component libraries, theming, tokens)
- Micro-frontends
- Collaborative/real-time editors (Google Docs-style) — advanced prompt
- Cross-browser/device considerations at scale

---

## How to use this file

Work top-to-bottom by tier, not by section — clear every T1 across all 11 sections before touching any T2. T1 is what gets asked regardless of company/seniority; T2 separates "memorized the definition" from "understands the tradeoff" (interviewers' favorite follow-up shape is "why not just—"); T3 is where senior/staff conversations go deeper, or where JD-specific tools (a listed state library, a listed testing tool) get pulled in.

*Caveat: tiers are inferred from public prep-platform signals (GreatFrontEnd importance tags/completion counts) and convergence across independent "Top N" lists — not a controlled frequency study. Treat boundaries as approximate.*
