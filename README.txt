🧱 Full Feature & Function Breakdown
🧩 CARD SYSTEM
addCard()

Creates a new draggable, resizable card

Initializes all internal sections and elements

Card Structure (DOM Layout)

Title input (<input type="text">)

Theme selectors (Primary / Secondary)

Stats section (STR, DEX, CON, INT, WIS, CHA)

Attributes section (HP, AC, Speed, etc.)

Spell slots (9 levels with 9 toggles each)

Funds tracker (CP, SP, EP, GP, PP)

Footer buttons (Generate Stats, Reset, Refit)

Textareas (Actions, Spells, Inventory, Notes)

Close button (X) in corner

Draggability

Uses addDragAndDrop(card) to make the card movable

Position is absolute within the container

Top of card is the handle

🎨 THEMING SYSTEM
primaryThemes[] / secondaryThemes[]

Array of hex color strings used for styling

Cards have two dropdowns to select these themes

updatePrimaryTheme(select)

Applies a gradient background based on selected primary theme

updateSecondaryTheme(select)

Colors inputs, buttons, borders, and focus styles using selected secondary theme

cycleTheme(button)

Automatically rotates to the next theme option

Updates both the primary and secondary theme selectors

🧮 STATS & ATTRIBUTES
makeSection(label, idx, labels, count, isStat)

Dynamically builds labeled input groups (e.g., "STR" + number input)

isStat true: input uses math evaluation

Used for both Stats and Attributes sections

evaluateMath(input)

Parses math in stat fields (e.g., 10 + 2)

Evaluates the result and displays it

Stores original expression in the tooltip (title)

✨ SPELL SLOT TRACKER
makeSpellSlots(idx)

Creates 9 rows, one for each spell level (0–8)

Each row: label + 9 clickable boxes (toggle filled/unfilled)

Toggle Logic

Clicking a slot toggles its class between filled/unfilled

Visual indication of used spell slots per level

💰 FUNDS TRACKER
makeFunds(idx)

Renders 5 labeled inputs for tracking:

CP, SP, EP, GP, PP

Regular editable number inputs (no evaluation)

🧰 FOOTER BUTTONS
Generate Stats

Button stub (currently no logic)

Potential future feature: auto-roll or assign stats

Reset Card

Clears all inputs and textareas within the card

Refit Card

Placeholder for resizing/layout adjustment logic

🧽 CARD MANAGEMENT
Close Button

X button in top-right corner

Removes the card from the DOM

Unique Card ID

Each card has a unique data-card-id or id

Used for scoping styles and logic to that specific card

🧼 UTILITY
Auto-evaluation

All stat inputs listen for change/blur

If a math expression is present, it's evaluated and shown

Theme Styling

Inline CSS styles (e.g., background, boxShadow)

Could be abstracted to CSS classes or external stylesheet for better maintainability

🚀 Suggested Extensions (Optional)
Persistence

Save/load cards to/from localStorage, IndexedDB, or backend

Resizing

Add draggable resize handles (use ResizeObserver or a library)

Dark Mode / Global Themes

Set app-wide dark/light modes with overrides per card

Modularize

Refactor into separate JS modules or components

Move to a modern framework (React, Vue, Svelte) for state and DOM handling

Export/Import

Export cards to JSON or printable format

Import from saved templates

Undo/Redo

Track changes for inputs and allow rollbacks
