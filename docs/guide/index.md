# Getting Started

Give the repository to an assistant with file and terminal access. Ask it to read README.md, AGENTS.md, and AI_SETUP.md and install a separate portal for your project. Provide the application and portal paths; existing files must be preserved.

## Manual fallback

Python 3.11+ and initial network access are needed. In the repository:

~~~sh
python scripts/portal.py setup
python scripts/portal.py check
python scripts/portal.py build
python scripts/portal.py serve --open
~~~

Open http://127.0.0.1:8000. Keep the terminal running; Ctrl+C stops it. Use serve --port 8001 for an occupied port. Reopen with the same command.

This is a local-only dev server for trusted documents. Do not expose it as a public production service.

## Adapt

Set project name/description in mkdocs.yml. Populate [Context](../PROJECT_CONTEXT.md) and [Current State](../CURRENT_STATE.md). Home/control status metadata comes from that same snapshot.

See [AI Workflow](AI_WORKFLOW.md), [Personalization](PERSONALIZATION.md), and [Document Map](../DOCUMENTATION_MAP.md).
