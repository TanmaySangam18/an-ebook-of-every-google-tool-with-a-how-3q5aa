ARCHITECT KNOWLEDGE (standing principles — build to these, they are graded):

• GROUNDING (cite-or-abstain): any feature that answers questions from data must retrieve first and
  answer ONLY from what it retrieved, citing the source records. If nothing relevant is retrieved, say so
  plainly ("no supporting record") — NEVER invent an answer. A confident wrong answer is the worst outcome.
• TENANT ISOLATION (deny-by-default): every data read is scoped to the current user/workspace FIRST, then
  filtered. One user's query must never be able to reach another's rows. Default to no-access; open access
  explicitly. When persistence is Supabase, rely on row-level security keyed to auth.uid — never a
  service-role key in a user-facing path.
• VERIFY BEFORE DONE: the feature is not done until it demonstrably runs — real GET/POST that persist,
  real empty/loading/error states, no console errors, a clean production build. Prefer standard, boring
  patterns that provably work over clever ones that might.
• ADOPT, DON'T INVENT: reach for proven, license-clean building blocks (the platform's own auth/storage,
  well-trodden libraries) before writing bespoke infrastructure. Every line you don't invent is a line
  that can't regress.
• INPUT DISCIPLINE: validate and type every input at the boundary; fail closed on bad input (4xx, never a
  500 or a silent wrong write).

Implement a small but REAL, working full-stack web app in this Next.js (App Router, TypeScript, Tailwind CSS) project for:

an ebook of every Google tool with a how-to for each

Requirements:
THIS IS A CONTENT PRODUCT, NOT A CRUD APP. Do NOT build a create/list/delete form. Do NOT build
app/api/items. Nobody is going to type entries into this; they are going to read it.

What to build instead:
- REAL WRITTEN CONTENT, and this is the whole product. Be exhaustive and specific. If the goal names
  a category, cover it properly: many entries, each with a real description someone could act on.
  Twenty thorough entries beat a hundred one-line stubs, and three entries is a failure however
  beautiful the page is.
- Put the content in a typed data file (lib/content.ts or similar) exporting a plain array, so it is
  editable without touching layout. Every entry gets a name, a one-line summary, and a short
  practical "how to use it" of two or three sentences.
- A reading layout: a clear index or grouped sections, in-page navigation to each section, and
  comfortable measure (max-w-prose or similar). It should feel like a document, not a dashboard.
- Search or filter across entries IS worth having, done client-side over the data file. No backend.
- No database, no API route, no forms. If you find yourself writing a POST handler, stop.

WRITE THE ACTUAL WORDS. Placeholder text, lorem ipsum, "TODO: add description", or three example
entries with a comment saying to add the rest all count as not having built the product.


DEPENDENCIES, AND THIS IS THE HARDEST RULE HERE:
- DO NOT add, import, or require ANY package that is not already in package.json. Not one.
- If you catch yourself typing an import for a package you have not seen in package.json, write the
  code without it instead. Node's standard library and what is already installed are enough.
- An import of a package that is not installed does not fail when you write it. It fails at
  `next build`, after all your work is done, and the whole build is thrown away. This single
  mistake is the most common way these builds die.
- Clean, responsive, no console errors. It must build with `next build` and run on Vercel.
- CODE MUST COMPILE: correct TypeScript types (no `any`-that-breaks), no unused imports/vars, only
  stable Next.js 16 App Router APIs. Prefer simple, standard patterns over clever ones.

DESIGN BAR — it must look like a senior product designer built it, NOT a generic AI template. Use
Tailwind and hold this bar (this is graded):
- Typography: a real hierarchy — one confident heading, clear secondary text, generous body
  line-height, tight tracking on large headings. Two weights only (normal + semibold).
- Space: an 8px rhythm (p-4/6/8, gap-4, space-y-6); generous whitespace; everything on a grid.
- Restraint: a neutral base (white / zinc) plus ONE accent color, used only for the primary action.
  No rainbow of colors, no heavy borders everywhere.
- Depth: subtle only — hairline borders (border border-zinc-200), rounded-xl cards, at most a light
  shadow. No decorative gradients, no neon, no emoji used as UI.
- Motion: gentle, purposeful transitions on hover/focus/state (transition duration-150). Never gratuitous.
- REAL states: design the empty state (an inviting prompt, not a blank), the loading state (skeleton or
  spinner), and the error state. They are part of the product, not afterthoughts.
- Detail: visible focus rings (focus-visible), hover states, mobile-first responsive layout, accessible
  labels and contrast.
- Voice: real, specific microcopy for THIS product (headings, buttons, empty-state text). Never lorem
  ipsum, never "get started by editing".
Aim for the calm, content-first polish of Linear / Stripe / Apple — clarity and restraint over decoration.