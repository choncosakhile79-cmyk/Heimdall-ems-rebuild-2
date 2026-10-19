# Heimdall EMS — Figma Design Handoff

**Purpose:** Translate the current Heimdall EMS web demo into a clean, editable Figma design system and prototype.  
**Source implementation:** `index.html` in this repository.  
**Product context:** A South African emergency medical services (EMS) coordination concept for a university marketing project.

## 1. Design direction

Keep the current Heimdall identity and blue palette. The goal is to make the existing working concept easier to present and refine in Figma—not to redesign it from scratch.

- **Brand feel:** calm, credible, fast, clinical, technology-enabled.
- **Primary blue:** `#0756C9`
- **Action blue:** `#0B72E7`
- **Signal sky blue:** `#47C7F5`
- **Deep navy:** `#061C3B`
- **Main text:** `#102846`
- **Muted text:** `#5F7390`
- **Page tint:** `#F6FAFF`
- **Soft blue surface:** `#EDF6FF`
- **Borders:** `#D8E6F6`
- **Success:** `#08A879`
- **Emergency / critical:** `#E7354D`
- **Typography:** Inter; use Inter in Figma, with a system sans-serif fallback in implementation.
- **Shape language:** rounded cards and controls, clear spacing, restrained shadows, high-contrast labels.
- **Existing colours:** preserve these as the baseline; do not replace them with a new palette.

## 2. Figma file pages

Create these pages in the Figma file, in this order:

1. **00 — Cover & Overview**: Heimdall EMS title, one-sentence purpose, project status, screen index.
2. **01 — Foundations**: colour styles, type scale, spacing, radius, elevation, icon guidance.
3. **02 — Components**: navigation, buttons, fields, role selector, status chips, cards, tables, modal, toast, map pins, theme toggle.
4. **03 — Public Website**: landing/home, about, contacts, sign-in and role selection.
5. **04 — EMS Operations**: dispatch dashboard, ambulance map, active incident details.
6. **05 — Nurse Portal**: incoming cases, patient handover summary, case details.
7. **06 — EMS Admin**: create/manage emergency case, incident list, fleet/readiness summary.
8. **07 — Hospital Admin**: hospital readiness, incoming patient/handover overview.
9. **08 — Patient Portal**: patient details, medical-aid verification, next-of-kin information.
10. **09 — Prototype Flows**: clickable paths for the main demo tasks.
11. **10 — Responsive & States**: desktop, tablet/mobile adaptations, empty/loading/error/success states, light/dark mode.

## 3. Recommended frames

Use a desktop frame of **1440 × 1000 px** for the primary web views and a **390 × 844 px** mobile frame for responsive examples. Use a 12-column desktop grid with 72 px outer margins and 24 px gutters as a starting point; adapt to the actual layout where needed.

### Public experience
- Landing page with clear headline, short value proposition, primary “Explore demo” / sign-in action, and restrained EMS imagery if the existing implementation uses it.
- About page explaining the concept and intended users.
- Contacts page with clearly labelled fictional demo contact details.
- Sign-in / role selection with four distinct options: **EMS**, **Nurse**, **EMS Admin**, **Hospital Admin**. Each role should have a visible demo-credential affordance if that exists in the current implementation.

### EMS operations
- Dispatch dashboard with incident queue, priority/status, summary cards, and map.
- Johannesburg street map using simple OpenStreetMap tiles; keep map labels and markers legible.
- Ambulance/fleet list and selected vehicle/incident detail.
- Case detail should make the incident number, priority, location, status, and handover notes easy to scan.

### Nurse portal
- Incoming/assigned cases with concise patient and incident summaries.
- A case detail/handover view with the minimum information needed for the demo.
- Clear status states (e.g. New, Assigned, En route, At scene, Handover complete) only where supported by the prototype.

### EMS Admin portal
- Create an emergency case form with patient name, surname, demo ID, address/location, priority, and relevant case summary.
- Incident list with consistent numbering and visible status.
- Fleet/readiness overview where implemented.

### Hospital Admin portal
- Hospital readiness and incoming-patient/handover overview.
- Status cards should use the same components and colour meanings as the EMS dashboard.

### Patient portal
- Patient details form/profile.
- Medical-aid status as a clear verification state, not as a real insurer connection.
- Next-of-kin details.
- If autosave is represented, show a visible “Saved” state and explain that it is demo/local behaviour where appropriate.

## 4. Components to build as Figma components

Use variants for state changes rather than duplicating components.

- **Button:** primary, secondary, quiet, destructive; default, hover, disabled, loading.
- **Input:** default, focused, filled, error, disabled; label, helper/error text.
- **Role card:** EMS, Nurse, EMS Admin, Hospital Admin; default and selected.
- **Status chip:** neutral, info, success, warning, critical.
- **Dashboard metric card:** label, value, helper text, optional icon.
- **Incident row/card:** case number, priority, location, status, time.
- **Map pin:** ambulance, incident, hospital; selected/unselected.
- **Navigation:** active/inactive item and mobile menu state.
- **Theme control:** light/dark.
- **Modal/dialog:** confirmation, case details, sign-in feedback.
- **Toast/alert:** success, warning, error, information.
- **Chat/FAQ panel:** closed, open, user question, answer, unavailable/error fallback if represented.
- **Form section:** heading, fields, validation, save state.

## 5. Prototype connections

Wire these flows so a reviewer can click through the design without guessing:

1. **Public site → role selection → sign-in → correct role dashboard.**
2. **EMS Admin → create incident → incident appears in the EMS and Nurse case lists.**
3. **EMS dashboard → select incident → view incident summary and map location.**
4. **Nurse → open incoming case → review handover summary.**
5. **Hospital Admin → incoming patients/readiness overview.**
6. **Patient Portal → update demo details → see medical-aid verification and next-of-kin information.**
7. **Theme toggle → light and dark variants of the same screen.**
8. **FAQ/chat control → open chat → submit question → display an answer or a clear fallback state.**

Keep each interaction focused and label prototype starting points. Do not make a static mock-up look like it is connected to live emergency dispatch or real patient systems.

## 6. Interaction, data and safety notes

- This is a **fictional demo**, not an operational emergency-response service.
- Map pins and ambulance movement are illustrative unless a real GPS source is explicitly integrated. Do not label simulated movement as live GPS tracking.
- Use fictional South African names, IDs, phone numbers and addresses in design examples.
- Medical-aid verification is a demo state; do not imply integration with an insurer.
- Chat/FAQ answers should be labelled as demo functionality unless an AI service is actually connected.
- Keep the incident numbering sequential and consistent across dashboards.
- Preserve role boundaries visually so users can tell which portal they are in.
- Dark mode should have its own colour styles and component variants; do not simply invert the whole screen.
- Include keyboard focus, readable contrast, clear validation, and large enough tap targets.

## 7. Design tokens

Suggested spacing scale (4 px base): **4, 8, 12, 16, 24, 32, 40, 48, 64 px**.  
Suggested radius scale: **8 px** for controls, **12 px** for cards, **16 px** for large panels.  
Suggested type scale: **12, 14, 16, 20, 24, 32, 40 px**. Use 16 px body text as the default and reserve large sizes for page titles and key metrics.

Create Figma colour styles using the hex values in Section 1. Create text styles for Display, H1, H2, H3, Body, Body Small, Label, and Caption.

## 8. Handoff checklist

- [ ] Build Foundations styles before drawing the screens.
- [ ] Create reusable components and variants.
- [ ] Use Auto Layout for navigation, cards, forms, tables and dashboard sections.
- [ ] Name layers and frames clearly (for example, `EMS / Dispatch Dashboard / Desktop`).
- [ ] Add prototype links for the eight flows above.
- [ ] Review desktop and mobile layouts.
- [ ] Review both light and dark modes.
- [ ] Mark simulated/live integrations accurately.
- [ ] Keep this Figma file aligned with the current `index.html` demo.

## 9. Importing the existing website into Figma

Figma does not turn a live website into a fully editable design file automatically. Use this handoff as the blueprint: open the published demo in a browser, capture the important screens at consistent sizes, then recreate them with Auto Layout and components. A website-to-Figma plugin may help with an initial import, but review the result and rebuild complex interactive elements as native Figma layers and prototype connections.

**Suggested file name:** `Heimdall EMS — Website & Dashboard Prototype`
