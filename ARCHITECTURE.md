System Architecture: Engineer's Toolkit
This document outlines the high-level architecture, design decisions, and data flow for the Engineer's Toolkit.

High-Level Overview
The Engineer's Toolkit is designed as a Static Single Page Application (SPA). The primary architectural philosophy is Zero Dependencies—the application requires no build steps (like Webpack or Vite), no external frontend frameworks (like React or Vue), and no backend servers or databases.
The entire application runs strictly entirely within the client's browser, relying on vanilla Web APIs for interaction, styling, and state management.

Core Technologies
HTML5: Semantic structure and built-in data repository (via hidden textareas).
CSS3: Responsive layouts (Flexbox/Grid), animations, and custom properties (CSS Variables) for dynamic theming.
Vanilla JavaScript (ES6+): DOM manipulation, event handling, clipboard interactions, and local storage management.

Data Management & State
Because the application is serverless and database-free, data is handled via two distinct client-side mechanisms:

1. Static Data (Prompt Repository)
The actual prompt content is baked directly into the HTML document.
Mechanism: Prompts are stored within visually hidden <textarea> elements at the bottom of the DOM.
Retrieval: When a user clicks a prompt card, the JavaScript engine looks up the target textarea via its unique ID, extracts the value, and injects it into the modal view.
Benefits: Instant retrieval times, no network latency, and extremely simple maintenance/customization.

2. Dynamic User State (Storage)
User-specific data and preferences are persisted across sessions using the browser's localStorage API.
Favorites: An array of card IDs saved by the user.
Recently Used: A queue of the last 6 copied prompt IDs.
Theme Preference: A boolean flag tracking if Dark Mode is active.

Logical Components
While not built with a component-based framework, the JavaScript logic is divided into distinct functional domains:
Theme & Role Controller
Listens to navigation clicks to swap the active view container.
Modifies the <body> class dynamically (e.g., ba-theme, pm-theme) to trigger CSS cascade changes, instantly applying role-specific color palettes globally.

Search Engine
A client-side filtering mechanism.
Listens to keyboard events in the search bar, parses the DOM for prompt cards, and applies inline display: none or display: flex styles based on title and description text matching.

Hub Renderer
Dynamically constructs the "My Hub" view.
Reads the arrays from localStorage, maps them to their original card nodes in the DOM, clones the HTML nodes, and injects them into the Hub grid.

Clipboard Manager
Utilizes the browser's Clipboard API (or fallback document.execCommand('copy')) to transfer text from the modal to the user's OS clipboard.
Triggers the "Toast" notification system upon successful execution.

Styling Architecture
CSS Variables: Extensive use of CSS custom properties at the :root level allows the application to swap entire color schemes instantly when toggling roles or switching to Dark Mode.
Glassmorphism: Navigation and modals utilize backdrop-filter: blur() for a modern, layered depth effect.
Responsive Grids: CSS Grid is used extensively (grid-template-columns: repeat(auto-fill, ...)) to ensure cards reflow seamlessly across mobile, tablet, and desktop viewports.

Security & Privacy
Since the application operates 100% locally:
No telemetry, tracking, or user data is sent over the network.
No backend API means zero exposure to traditional server-side vulnerabilities (SQLi, Server-side XSS).
