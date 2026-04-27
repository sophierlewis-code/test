# Services Section Review & Improvement Plan

This note captures practical improvements for the Framer `ServicesSection` component so it reads as more premium, remains editable by non-technical teammates, and behaves predictably across breakpoints.

## 1) Immediate fixes (high impact)

1. **Replace smart quotes with standard quotes in code.**
   - The snippet uses typographic quotes (`“ ”` and `‘ ’`) in imports, strings, and selectors.
   - TypeScript/JSX will fail to parse until these are replaced with plain quotes (`"` / `'`).
2. **Strengthen 3×2 layout semantics.**
   - The current 3×2 variant intentionally places header in the first tile and 5 service cards in the remaining cells (good concept).
   - Explicitly enforce six cells only in this mode to avoid accidental overflow when content configuration changes.
3. **Improve visual hierarchy in first card row.**
   - The header tile is currently visually close to service tiles.
   - Increase heading contrast and vertical spacing so the header reads as a section anchor, not a sixth service card.

## 2) Content architecture (for a consultancy feel)

Use this message structure in every card:
- **Title:** outcome-led and specific (5–7 words)
- **Description:** one sentence with a clear business result
- **Meta line:** only key delivery methods (3–5 terms)

### Suggested service set (5 cards)

1. **Technical Writing & Editing**
   - Outcome: decision-ready documents for clients/donors.
2. **Applied & Participatory Research**
   - Outcome: evidence generation grounded in field realities.
3. **Policy Outreach & Advocacy**
   - Outcome: research translated into stakeholder action.
4. **Strategic Planning & Advisory**
   - Outcome: clear strategic direction and implementation path.
5. **Capacity Development**
   - Outcome: stronger team capability and execution quality.

## 3) Premium UI adjustments

1. **Reduce icon competition.**
   - Keep icon opacity low (0.12–0.16) and ensure titles remain the dominant focal point.
2. **Tighten typography scale.**
   - Card title: 20px semibold (current direction is good).
   - Body: 15–16px with 1.6–1.7 line-height.
   - Meta: 12–13px with reduced contrast.
3. **Add consistent vertical rhythm.**
   - Use fixed internal spacing tokens (e.g., 8 / 12 / 16 / 24 / 32).
4. **Avoid overly decorative hover.**
   - Keep hover as subtle lift + shadow shift; avoid scale on dense grids to preserve clean enterprise feel.

## 4) Responsive behavior guidance

1. **Desktop (>=1100px):**
   - 3-column layout with comfortable gutters.
2. **Tablet (~700–1099px):**
   - switch to 2 columns or horizontal carousel depending on available width.
3. **Mobile (<700px):**
   - single-column cards with simplified padding.

## 5) Framer-specific maintainability recommendations

1. Keep `layout` options but treat `Grid3x2` as a dedicated opinionated preset.
2. Group property controls for editors:
   - Content (kicker, heading, subtitle, services)
   - Layout (mode, columns, spacing)
   - Style (colors, radius, shadow)
   - Typography (fonts)
3. Keep sensible defaults for non-design users so first drop-in already looks polished.

## 6) Accessibility and UX checks

1. Maintain sufficient contrast (especially muted/meta text).
2. Ensure headings are semantic (`h2` section heading, `h3` card headings).
3. Keep carousel dots keyboard accessible and add visible focus states.

## 7) Priority implementation roadmap

1. **P1:** fix quote characters + parsing stability.
2. **P1:** lock 3×2 structure and spacing consistency.
3. **P2:** refine typography/contrast for premium tone.
4. **P2:** improve tablet/mobile behavior.
5. **P3:** tidy Framer control grouping and editor defaults.

---

If helpful, the next step is to produce a cleaned **drop-in TSX version** with:
- corrected syntax,
- simplified style tokens,
- and a stricter `Grid3x2` preset geared to consultancy presentation.
