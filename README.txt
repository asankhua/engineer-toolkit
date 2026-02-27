🛠️ Engineer's Toolkit | Full Lifecycle Hub

Engineer's Toolkit is a lightweight, fully interactive Single Page Application (SPA) designed to bridge business strategy with technical execution. It provides a curated, role-specific collection of AI prompts tailored for the entire Software Development Life Cycle (SDLC) — helping Business Analysts, Project Managers, Architects, Developers, and Testers supercharge their AI workflows.

✨ Features

🎭 Role-Based Workspaces: Instantly switch between custom-themed hubs for 5 distinct engineering roles (BA, PM, Architect, Developer, Tester).

🔍 Global Real-Time Search: A sleek search bar that instantly filters prompts across all categories by title or keyword.

🌓 Dark/Light Mode: Seamless toggle between a crisp light mode and a deep, professional dark mode. Your preference is automatically saved.

⭐ My Hub (Favorites & Recents): Save your most-used prompts to your personal Hub using the star icon. The app also automatically tracks your 6 most recently copied prompts. All data is saved securely in your browser's localStorage.

📋 One-Click Copy: Preview prompts in a sleek modal and copy them instantly to your clipboard with premium toast notifications.

⚡ Zero Dependencies: Built entirely with vanilla HTML, CSS, and JavaScript. No build steps, frameworks, or databases required.

👥 Roles & Prompts Included

Business Analyst (BA): User Stories, Gap Analysis, Use Cases, Process Modeling (Mermaid JS), API Specs.

Project Manager (PM): Project Charters, WBS Generators, Risk Registers, Executive Status Reports, Conflict Resolution.

Architect: High-Level Design (HLD), Microservices Extraction, Cloud Setup, Threat Modeling, ADR Generators.

Developer: Boilerplate Generation, Complex Logic Builders, Regex Wizards, SQL Optimization, Bug Hunting, TDD.

Tester (QA): Happy Path Architect, Negative Scenarios, Edge Case Destructor, BDD/Gherkin, API Contract Testing, Accessibility Audits.

🚀 How to Use

Since this application is a pure front-end tool, getting started takes literally one second:

Clone or Download this repository.

Open index.html directly in any modern web browser (Chrome, Firefox, Safari, Edge).

Find your Task: Select your role and find the prompt tile that matches your current goal.

Copy the Prompt: Click "View Prompt" and copy the text.

Paste to AI: Open ChatGPT, Gemini, or Claude, paste the prompt, and answer the contextual questions it asks you one by one!

🛠️ Customization

Want to add your own prompts? It's incredibly easy:

Open index.html in your text editor.

Scroll down to the <!-- Hidden Prompt Repository --> section.

Add a new <textarea id="your-custom-id">Your prompt text here...</textarea>.

Add a new card in the respective Role section calling openPrompt('Card Title', 'your-custom-id').

📜 License

© 2026 ASHISH KUMAR SANKHUA. ALL RIGHTS RESERVED.
