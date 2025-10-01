# Mermaid Editor (AI)

A lightweight, single-file, backend-free web editor for Mermaid diagrams with AI assistance.

- Fast editing of Mermaid diagrams
- Live preview with zoom and pan
- Multiple projects stored locally (localStorage)
- AI chat via OpenRouter to apply changes to Mermaid code
- Lightweight Mermaid syntax highlighting
- Click nodes/edges in Preview to highlight corresponding code

This repo is ready for static hosting (GitHub Pages, Vercel Static, Netlify).

## Prerequisites

- Modern browser (Chrome/Edge/Firefox/Safari)
- OpenRouter API key for AI chat

## Quick Start

1. Clone/download the repo and open `index.html` in your browser.
2. Click “AI Chat” in the header, enter your `sk-or-...` key, and click “Save Key”. The key is stored only in your browser (localStorage).
3. Use the “Projects” panel to create/rename/delete projects. Each project’s code is saved locally.
4. Type in “Mermaid Code” and press Ctrl/Cmd+Enter to render. Clicking nodes/edges in “Preview” will highlight the corresponding code line.

## Features

- Local Projects: simple CRUD (New/Rename/Delete) + click to switch
- Two initial samples created on first run: “Sample Flowchart” and “Advanced Sample”
- Undo/Redo: toolbar buttons (↶/↷) and standard shortcuts
- Export: SVG/JPG and `.mmd` text
- Zoom/Pan the preview via mouse and toolbar
- AI Chat: default model `google/gemini-2.5-flash` through OpenRouter

## OpenRouter

This editor calls `https://openrouter.ai/api/v1/chat/completions`. To use AI chat:

- Click “AI Chat”
- Enter your `sk-or-...` key and click “Save Key”
- Type requests like “add a new node between A and B”

Security note: The key is stored in localStorage and only sent to OpenRouter. For public deployments, consider a secure server-side proxy instead of direct client-side keys.

## Shortcuts

- Ctrl/Cmd+Enter: Render
- Ctrl/Cmd+S: Save current code to localStorage
- Ctrl/Cmd+Z: Undo
- Ctrl/Cmd+Y or Shift+Ctrl/Cmd+Z: Redo
- Tab: Insert two spaces

## Development Notes

- Single-file app: all CSS/JS is in `index.html`
- History and zoom/pan state are persisted in localStorage
- To deploy, serve `index.html` from any static host

## Deployment (GitHub Pages)

- User/Org site: create a repo named `USERNAME.github.io`, push, then open `https://USERNAME.github.io`
- Project site: enable Pages in Settings → Pages (Branch: `main`, Folder: `/`), then open `https://USERNAME.github.io/REPO_NAME/`

## Roadmap (suggested)

- Language switcher (EN/FA)
- Richer syntax highlighting (tokenization)
- Import/Export projects (JSON)
- Secure server-side proxy for OpenRouter

## Contributing

PRs are welcome. Please keep UI/UX changes small and isolated and include clear descriptions.

## License

MIT License
