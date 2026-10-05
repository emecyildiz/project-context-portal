# Project Context Portal

An AI-ready, local-first project portal for architecture, decisions, plans, progress, and evidence. Designed for setup and maintenance by AI coding assistants.

Give this repository to your coding assistant. Let it inspect your project, set up the portal, and maintain the project memory while you browse a readable local website.

## Start with your AI

Copy this prompt and replace the paths:

> Read README.md, AGENTS.md, and AI_SETUP.md in https://github.com/emecyildiz/project-context-portal. Set up the portal in [portal directory] for my project at [project directory]. Preserve existing files and instructions. Adapt explanations and working style to my preferences. Do not invent project facts. Verify the portal and show me its local URL.

The assistant needs file/repository and terminal access. A chat-only model can guide you but cannot install software on your computer. A URL alone does not guarantee that every tool fetches the files.

## Included

- Home, control center, product, architecture, planning, decisions, research, evidence, glossary, and work log.
- Git-tracked Markdown as project memory; search, diagrams, responsive layout, light/dark themes.
- Proposed / Validating / Implemented / Verified / Deferred / Rejected distinctions.
- Provider-neutral agent runbook and optional private communication preferences.
- One Python command for setup, checks, build, and serving.
- An explicitly fictional example, separate from your project's real state.

No AI API key, hosted database, or provider SDK is needed by the portal. Your chosen coding assistant operates outside it.

## Manual fallback

Python 3.11+ is required. From this repository:

~~~sh
python scripts/portal.py setup
python scripts/portal.py check
python scripts/portal.py build
python scripts/portal.py serve --open
~~~

Use your actual Python executable (for example python3) if python is unavailable. Setup downloads dependencies into a local .venv, not globally. Direct dependency versions are pinned; transitive dependencies are not fully locked. Serve binds to 127.0.0.1:8000; stop with Ctrl+C. Use --port 8001 if needed. The foreground server needs its terminal; no permanent service is installed.

## Personalization

Adapt language, tone, friendliness, explanation depth, technical background, and pace to explicit preferences and the current conversation. Ask only what matters. Style never overrides factual accuracy, evidence, privacy, permissions, or honest test reporting.

With consent, use templates/USER_PREFERENCES.example.md to create .portal/user-preferences.local.md. That directory is Git-ignored and outside the website. Private preferences are not automatically shared across machines.

## Adaptation and honest limits

Change site_name and site_description in mkdocs.yml; populate docs/PROJECT_CONTEXT.md and docs/CURRENT_STATE.md from actual evidence. The home/control badges use that same state metadata at build time, not copied statuses.

The starter is English. Agents can translate project documents and set the theme language; full automatic translation is not built in. A separate adjacent portal directory is the safe default; never blindly merge this template into an application's root.

This is a documentation portal, not an autonomous manager. It does not import all chats, edit tasks in the browser, run application tests, or enforce agent obedience. People/agents must maintain the documents. Passing a portal build does not verify the user's application.

## Development

~~~sh
python -m unittest discover -s tests -v
python scripts/portal.py check
python scripts/portal.py build
~~~

See RELEASE.md for actual toolkit verification; portable code alone does not prove macOS/Linux execution.

## License and credits

MIT, approved by the project owner. Dependencies retain their own licenses; see THIRD_PARTY_NOTICES.md. Built on MkDocs and Material for MkDocs. No graduation-project documents, circuits, or private transcripts are included.

https://github.com/emecyildiz/project-context-portal
