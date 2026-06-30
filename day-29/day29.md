# Day 29: Operation Lifeline — Supply Chain Crisis Lab

## What I Built
A single-file HTML simulation game where you play a Chief Supply Chain Officer navigating a randomly generated business crisis. Built with React (CDN) + Babel, fully offline, zero dependencies.

**Flow:** Welcome → Random Company Generation → Random Crisis Event → War Room (pick 3 of 6 response actions) → 4-Round Supplier Negotiation → CEO Boardroom (5 leadership MCQs) → AI Strategy (pick 2 of 5 AI investments) → Final Dashboard with full performance debrief.

Every playthrough randomizes the company profile, the crisis type (8 possible: factory fire, supplier bankruptcy, port strike, cyberattack, flood, raw material shortage, political conflict, shipping delay), and question order — so no two runs play the same.

## Why I Built It
Supply chain management is abstract until you feel the trade-offs. I wanted to simulate the actual tension between cost, speed, inventory, and customer trust that real COOs face — and teach the "why" behind each decision, not just the "what."

## Tech Stack
- React 18 (CDN) + Babel Standalone (in-browser JSX)
- Vanilla CSS (dark enterprise dashboard theme, CSS variables, animated progress bars)
- No backend, no APIs, no build step — opens directly in any browser

## Verbatim Prompts Used
1. "You are an expert frontend developer, UX designer, game designer, and supply chain consultant. Build it so a complete beginner can play it — plain language, context before every decision, 'why does this matter' explanations... Build a complete single-file HTML app named 'Operation Lifeline: Supply Chain Crisis Lab'... [full requirements: React CDN + Babel JSX, premium dark theme, 8-step flow, randomized company/crisis generation, War Room with 6 actions, 4-round negotiation, CEO boardroom, AI strategy, final dashboard]"
2. "the file is appearing black only no content solve the issue" — debugging request after initial render failure

## Architecture
```
operation_lifeline.html
├── <style> — dark dashboard design system (CSS vars, cards, progress bars, badges)
└── <script type="text/babel">
    ├── Utilities (rnd, pick, shuffleArr, clamp, scoreColor)
    ├── Data (industries, crises pool, war room actions, negotiation rounds, CEO questions, AI investments)
    ├── Components
    │   ├── ProgressBar — animated metric bars
    │   ├── PhaseBar — sticky progress dots
    │   ├── WelcomeScreen
    │   ├── CompanyProfile — randomized company card generator
    │   ├── CrisisAlert — randomized crisis with impact stats
    │   ├── WarRoom — select 3 of 6 actions, simulates 5 metrics
    │   ├── Negotiation — 4 branching rounds, Trust/Price/Lead Time tracking
    │   ├── CEOBoardroom — 5 MCQs with instant expert explanations
    │   ├── AIStrategy — select 2 of 5 AI investments
    │   └── FinalDashboard — weighted overall score + personalized feedback
    └── App — phase router using renderScreen() with explicit if/else
```

## Key Learnings
1. **React CDN apps fail silently on render errors.** My first build used an object-literal map of `{ phase: <Component/> }`, which eagerly evaluates every JSX element on every render — including phases with `null` props. One bad prop access crashed the whole tree with zero console feedback, leaving just the dark CSS background. Fixed by switching to a `renderScreen()` function with explicit `if` conditionals that only construct the active phase's element.
2. **Null guards are non-negotiable in multi-phase apps.** Every component that depends on async-generated state (company, crisis, questions) now has an early `if (!data) return null;` guard, since phase transitions can theoretically outrace state setting.
3. **Arrow functions inside JSX props are fine, but traditional function declarations for the data/utility layer improved Babel-in-browser compatibility and made stack traces more readable during debugging.**
4. **Pinning CDN versions** (`react@18.2.0`, not `@18`) prevents silent breakage if a CDN ships a patch update mid-project.
5. **Destructuring `useState` via `var [x, setX] = useState()` pattern with explicit array indexing** (`var state = useState(...); var x = state[0];`) made the component logic easier to debug line-by-line when isolating the render crash.

## File Tree
```
day29_supply_chain_crisis_lab/
├── operation_lifeline.html
└── day29.md
```

## Stats
| Metric | Value |
|---|---|
| File size | ~68 KB |
| Lines of code | ~1,340 |
| Components | 10 |
| Randomized crisis types | 8 |
| War Room actions | 6 (pick 3) |
| Negotiation rounds | 4 |
| CEO questions | 5 |
| AI investment options | 5 (pick 2) |
| External dependencies | React, ReactDOM, Babel (CDN only) |

## Next Actions
- Add a difficulty modifier (randomized crisis severity multiplier)
- Add a "compare to last run" stat persistence using localStorage-free in-memory session history
- Expand crisis pool to 12+ scenarios
- Add a printable/exportable summary report view

## Hashtags
#ABTalksOnAI #60DayClaudeChallenge #SupplyChain #ReactJS #BuildInPublic #ClaudeAI #SystemDesign #SupplyChainManagement #IndieHacking #DataScience #PromptEngineering