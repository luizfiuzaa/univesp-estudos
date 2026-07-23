# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is **not a software project** — it is an [Obsidian](https://obsidian.md) vault of personal study notes for a UNIVESP **Engenharia da Computação** (Computer Engineering) degree. Content is Markdown (`.md`) plus supporting `.pdf` course materials. There is no build, no tests, and no runtime.

**All note content is written in Brazilian Portuguese (pt-BR).** Match this language when creating or editing notes.

## Version control

The vault is synced with the [obsidian-git](https://github.com/Vinzent03/obsidian-git) plugin, which produces automatic backup commits (e.g. `vault backup: 2026-07-22 11:26:49`) alongside manual ones. When committing:
- Keep commit messages in Portuguese, matching the existing style (e.g. `começando modulo 2`, `finalizado modulo 1 IA`).
- Expect `.obsidian/workspace.json` to show as modified constantly — it stores local UI state and is noise, not meaningful change.
- `.DS_Store` and `.obsidian/` local files are tracked (no `.gitignore` exists); don't add new machine-specific clutter.

## Directory structure

Notes follow a strict, meaningful hierarchy. Preserve it when adding content:

```
Engenharia-da-Computação/
  <Disciplina>/                          e.g. "Inteligência Artificial na Prática Acadêmica e Profissional"
    Quinzena/                            "Fortnight" — the course's two-week study cycle
      Q<n>/                              Quinzena number (Q1, Q2, …)
        Módulos/
          M<n>/                          Module number (M1…M6)
            <NOTA>.md                    the study note(s)
            <material>.pdf               course PDFs (e-book, apostila)
```

Each discipline mirrors the same `Quinzena/Q<n>/Módulos/M<n>/` skeleton.

> Note: git history shows notes migrating from an older `Módulos/M<n>/` layout (at the discipline root) into the newer `Quinzena/Q<n>/Módulos/M<n>/` layout. When in doubt, follow the `Quinzena/` structure — it is the current convention.

## Note conventions

Video-lesson notes follow a consistent template (see the `Inteligência Artificial` module notes as reference):

1. **Video embed** on line 1 — a bare YouTube URL in Markdown image syntax: `![Título](https://youtu.be/<id>)` (rendered by the `video-embed` plugin).
2. **Summary blockquote** — one `>` paragraph describing the lesson.
3. **Content sections** using `####` headers for concepts, with `**termo:**` bold lead-ins for key terms and definitions.
4. **`### Material Base`** section at the end, linking each PDF twice — an `online` link to the `assets.univesp.br` URL and a `local` link to the file sitting next to the note:
   ```
   > [m1-ebook online](https://assets.univesp.br/disciplinas/COM170/pdf/quinzena-1/m1-e-book.pdf)
   > [m1-ebook local](m1-e-book.pdf)
   ```

Note filenames often encode the lesson type in caps, e.g. `(VIDEO AULA 01) O QUE É IA REALMENTE?.md`. Keep this pattern for new lesson notes.

## Obsidian plugins in use

Enabled community plugins (`.obsidian/community-plugins.json`) that affect how notes render — respect their syntax:
- **dataview** — queries over note metadata; watch for ```` ```dataview ```` code blocks.
- **video-embed** — renders the bare-URL video embeds described above.
- **obsidian-excalidraw-plugin** — `.excalidraw` drawings.
- **calendar**, **table-editor-obsidian**, **obsidian-git**.

Prefer `[[wikilink]]`-style internal links and standard Obsidian Markdown so notes stay usable inside the app.
