# Toolkit release status

Target: v0.1.0
Status: Verified (local toolkit checks only)
Date: 2026-10-05

This describes the toolkit, not a user's tracked application.

Implemented scope: generic Markdown portal, provider-neutral onboarding, optional private style preferences, local setup/build/serve, shared state metadata, content checking, and normal/negative unit tests.

Verification on Windows with Python 3.12.14: local setup completed, 19 unit tests passed, content checks passed, and the strict MkDocs build passed. A live loopback preview was reviewed in the browser: main sections, search, and the fictional Mermaid example worked. No browser warning/error logs were observed during the review.

See [the dated verification record](verification/2026-10-05.md) for methods and limits. GitHub publication is a separate Git operation; this file does not assert a tag or a hosted deployment.

Windows is the initial local target. macOS/Linux must not be advertised as tested until run there. No separate LLM installation/adaptation session has been tested; instructions are best-effort contracts, not certified provider integrations.
