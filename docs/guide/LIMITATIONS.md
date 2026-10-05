# Limitations

- Static documentation with a local dev server, not a multi-user task app.
- No browser editing, accounts, automatic chat import, provider SDK, built-in inference, or autonomous tasks.
- No application tests or task approvals run from the website.
- Agent instructions are best effort, not guaranteed across every LLM/configuration.
- People/agents must maintain underlying facts. Shared state metadata avoids copied badges but does not prove freshness.
- The content checker covers ordinary inline Markdown and HTML href/src links, not every Markdown construct, remote URL, or fragment anchor. Strict MkDocs builds add separate checks.
- Personal preferences are excluded by layout and Git ignore, not encryption. Review tracked files and generated pages before publishing.
- Dependencies and browser/diagram assets may have network requirements; completely offline Mermaid rendering is not promised.
- Tested environments are listed in RELEASE.md; portable paths alone are not cross-platform evidence.
- GitHub template copies do not automatically receive updates.
