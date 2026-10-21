# SkillConnect Landing Page Prompt

```markdown
Build a clean, high-impact hero landing page for a community workforce platform called "SkillConnect" using React, Tailwind CSS, and Vite. The page should be a single viewport-height section with a sunlit city hero banner showcasing diverse local skilled workers, bold value-proposition typography, dual primary CTAs, a floating handwritten community badge, and a bottom value-proposition feature bar.

**Hero Visual & Background:**
- Top background features an airy, bright daylight sky with subtle sunlit clouds, transitioning into a modern city skyline with towers and construction cranes.
- Right hero side features a high-resolution panoramic image of diverse, smiling local professionals and trade workers standing shoulder-to-shoulder:
  - Center foreground: smiling construction worker wearing a yellow hard hat, safety glasses, and a high-vis neon orange safety vest with reflective stripes over a blue work shirt, carrying tools/rebar over his shoulder.
  - Alongside him: a female gardener/landscaper holding a lush potted green plant, a mechanic in a blue baseball cap holding a chrome wrench, a site engineer in a white hard hat and collared shirt, a master chef in a white chef's toque and apron with folded arms, and an assistant worker in an orange vest.
- Subtle gradient fade from the left (white/light sky blue) ensures the hero headline, subtext, and buttons remain 100% legible across all screen sizes.
- In the top-right above the workers, include a floating tilted handwritten note with a swooping arrow underline flourish:
  "Local Skills Create Stronger Communities" in deep navy script (`font-handwriting`, tilted ~ -5deg).

**Fonts (loaded in index.html):**
1. "Inter" or "Plus Jakarta Sans" from Google Fonts (weights 400, 500, 600, 700, 800) -- used for brand name, headings, navigation links, body text, buttons, and feature cards. Register as `fontFamily.sans`.
2. "Caveat" from Google Fonts (weights 600, 700) -- used for the floating handwritten community note. Register as `fontFamily.handwriting`.

**Icons:**
Use `lucide-react` for all icons:
- `Search` (for "Find a Job" CTA)
- `Users` (for "Find a Worker" CTA and "Build Communities" feature badge)
- `ArrowRight` (for CTA button direction arrows)
- `MapPin` (for "Local Opportunities" feature badge)
- `ShieldCheck` (for "Trusted Profiles" feature badge)
- `Zap` (for "Quick & Easy" feature badge)
- `Menu` and `X` (for responsive mobile navigation toggle)

**Logo & Brand Identity:**
- Custom SVG logo icon: Two abstract stylized human figures seated together:
  - Left figure in vibrant emerald green (`#16a34a`), rounded head and curved torso.
  - Right figure in deep navy blue (`#0f2744`), rounded head and curved torso overlapping the green figure.
- Brand name: "SkillConnect" in deep navy (`#0f172a`), extra bold, `text-xl sm:text-2xl`, `tracking-tight`.
- Tagline directly below brand name: "Local Work • Local People • Stronger Communities" in `text-[10px] sm:text-xs`, `text-slate-500`, font-normal tracking-wide.

**Navbar:**
- Horizontal bar at the top with responsive padding (`px-6 sm:px-10 lg:px-16`, `py-4 sm:py-5`), clean white/translucent background with subtle bottom border (`bg-white/80 backdrop-blur-md border-b border-slate-100`).
- Left: Brand logo icon + "SkillConnect" + tagline.
- Center (hidden below `md`): Four nav links -- "Home", "Find Jobs", "Find Workers", "About" in `text-sm font-medium`:
  - "Home": Active state in emerald green (`text-emerald-700 font-semibold`) with an active green indicator bar beneath it (`w-6 h-0.5 bg-emerald-600 rounded-full mx-auto mt-1`).
  - "Find Jobs", "Find Workers", "About": Neutral slate (`text-slate-700 hover:text-emerald-700 transition-colors`).
- Right (hidden below `md`):
  - "Login": Rounded pill button (`rounded-full border border-slate-300 hover:border-slate-400 text-slate-800 px-6 py-2.5 text-xs sm:text-sm font-medium hover:bg-slate-50 transition-all`).
  - "Sign Up": Rounded pill button (`rounded-full bg-emerald-700 hover:bg-emerald-800 text-white px-6 py-2.5 text-xs sm:text-sm font-semibold shadow-sm hover:shadow transition-all`).
- Right (visible below `md`): Hamburger icon button (`Menu`, `w-6 h-6`, `text-slate-800`).

**Mobile Menu Overlay (below `md` only):**
- Fixed fullscreen overlay (`fixed inset-0 z-50 bg-white/95 backdrop-blur-lg`).
- Toggles visibility via React `useState` -- animated with `opacity` and `transform` transitions.
- Header row matches navbar: brand logo on left, `X` close icon on right.
- Centered vertically: the 4 navigation links rendered in `text-2xl font-bold text-slate-900 hover:text-emerald-600 transition-colors` with staggered entrance animation delays (`transitionDelay: i * 80 + 100ms`).
- Bottom row: full-width "Login" and "Sign Up" buttons.
- All links and buttons call `setMenuOpen(false)` on click.

**Hero Content (vertically centered, left-aligned):**
All left hero elements use staggered `animate-fade-up` animations (defined in CSS as `@keyframes fade-up` translating from `translateY(24px), opacity:0` to `translateY(0), opacity:1` over `0.7s ease-out`). Each successive element has an additional `0.15s` delay. Elements start with `opacity: 0` and use `animation-fill-mode: forwards`.

1. **Main Heading:** Three stacked lines in bold modern sans-serif, tight tracking (`tracking-tight`), crisp line-height (`leading-[1.08]`), using `text-4xl sm:text-5xl lg:text-6xl xl:text-[4.25rem] font-extrabold`:
   - "Find Work." (deep navy `text-slate-900`)
   - "Find Workers." (deep navy `text-slate-900`)
   - "Build Your Future." (vibrant emerald green `text-emerald-700`)
   Uses `animate-fade-up` (0.1s delay).

2. **Subtext:**
   "Connect with trusted local workers and nearby job opportunities based on skills, location, availability and experience."
   In `text-slate-600`, `text-base sm:text-lg`, `leading-relaxed`, `max-w-md lg:max-w-lg`, `mt-5 sm:mt-6`.
   Uses `animate-fade-up-delay-1` (0.25s delay).

3. **CTA Row:**
   `mt-8 sm:mt-10 flex flex-wrap items-center gap-3 sm:gap-4`.
   Uses `animate-fade-up-delay-2` (0.4s delay).
   - Primary Pill Button: "Find a Job" with `Search` icon on left and `ArrowRight` icon on right. `bg-emerald-700 hover:bg-emerald-800 text-white rounded-full px-7 py-3.5 sm:py-4 text-sm sm:text-base font-semibold shadow-md shadow-emerald-700/25 flex items-center gap-2.5 transition-all group hover:scale-[1.02]`. Arrow slides right slightly on hover (`group-hover:translate-x-1 transition-transform`).
   - Secondary Pill Button: "Find a Worker" with `Users` icon on left and `ArrowRight` icon on right. `bg-white hover:bg-slate-50 text-slate-800 border border-slate-200 hover:border-slate-300 rounded-full px-7 py-3.5 sm:py-4 text-sm sm:text-base font-semibold shadow-sm flex items-center gap-2.5 transition-all group hover:scale-[1.02]`. Arrow slides right slightly on hover (`group-hover:translate-x-1 transition-transform`).

**Bottom Value-Proposition Feature Bar:**
A clean horizontal card strip spanning across the bottom with a subtle top border (`border-t border-slate-100 bg-white shadow-sm`):
- 4-column responsive grid (`grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 divide-y sm:divide-y-0 sm:divide-x divide-slate-100 px-6 sm:px-10 lg:px-16 py-6 sm:py-8`).
- Uses `animate-fade-up-delay-3` (0.55s delay).
- Four feature items, each pairing a colored circular icon badge with two lines of descriptive text:
  1. **Local Opportunities:**
     - Circular icon badge: emerald green background (`w-11 h-11 rounded-full bg-emerald-600 text-white flex items-center justify-center shadow-sm`) with `MapPin` icon (`w-5 h-5`).
     - Text: Title "Local Opportunities" (`text-sm sm:text-base font-semibold text-slate-900`) / Subtext "Jobs and workers near you" (`text-xs sm:text-sm text-slate-500 mt-0.5`).
  2. **Trusted Profiles:**
     - Circular icon badge: royal blue background (`w-11 h-11 rounded-full bg-blue-600 text-white flex items-center justify-center shadow-sm`) with `ShieldCheck` icon (`w-5 h-5`).
     - Text: Title "Trusted Profiles" (`text-sm sm:text-base font-semibold text-slate-900`) / Subtext "Verified and reliable" (`text-xs sm:text-sm text-slate-500 mt-0.5`).
  3. **Quick & Easy:**
     - Circular icon badge: golden amber background (`w-11 h-11 rounded-full bg-amber-500 text-white flex items-center justify-center shadow-sm`) with `Zap` icon (`w-5 h-5`).
     - Text: Title "Quick & Easy" (`text-sm sm:text-base font-semibold text-slate-900`) / Subtext "Simple and fast process" (`text-xs sm:text-sm text-slate-500 mt-0.5`).
  4. **Build Communities:**
     - Circular icon badge: violet/indigo background (`w-11 h-11 rounded-full bg-indigo-600 text-white flex items-center justify-center shadow-sm`) with `Users` icon (`w-5 h-5`).
     - Text: Title "Build Communities" (`text-sm sm:text-base font-semibold text-slate-900`) / Subtext "Support local employment" (`text-xs sm:text-sm text-slate-500 mt-0.5`).

**CSS Animations (defined in index.css under `@layer utilities`):**
```css
@keyframes fade-up {
  from { opacity: 0; transform: translateY(24px); }
  to { opacity: 1; transform: translateY(0); }
}
@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}
@keyframes scale-in {
  from { opacity: 0; transform: scale(0.95); }
  to { opacity: 1; transform: scale(1); }
}
```
With classes: `.animate-fade-up` (0.1s delay), `.animate-fade-up-delay-1` through `.animate-fade-up-delay-3` (0.15s increments, starting `opacity: 0`), `.animate-fade-in`, and `.animate-scale-in`.

**Responsive behavior:**
- Mobile-first breakpoints at `sm` (640px), `md` (768px), and `lg` (1024px).
- Navigation links and auth buttons show on `md`+; hamburger icon shows below `md`.
- Hero layout stacks on mobile with content leading and workers visual supporting, then transitions to an expansive side-by-side panoramic layout on desktop.
- Bottom feature bar arranges in 1 column on mobile, 2 columns on tablet (`sm`), and 4 columns on desktop (`lg`) with subtle vertical dividers.
- All headings and spacing use responsive scaling (`text-4xl sm:text-5xl lg:text-6xl xl:text-[4.25rem]`, `px-6 sm:px-10 lg:px-16`).

Make everything fully mobile responsive. Use a single `App.tsx` component with `useState` for the mobile menu toggle. No routing needed.
```
