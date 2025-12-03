# Project Context — Descent-2-MVL-tools

Purpose
- Tools to convert user-supplied MP4 videos into MVE/MVL cutscene formats for use with d2x-xl.
- Emphasis: this is primarily a learning project to understand media conversion, format internals, and tool-building with AI assistance.

High-level goals
- Understand the MVE/MVL container and write tools to produce valid MVE frames from modern MP4 sources.
- Produce a robust encoder that preserves timing/audio sync and creates MVL packages usable by d2x-xl.
- Keep all game assets out of the repo; tools only. Users provide their own legally obtained media.

Current status (short)
- Language: C++
- Iterative workflow: generate code with Copilot/ChatGPT → compile/run locally → paste outputs/errors into chat → accept/refine → repeat.
- Status: progressing incrementally. Many small successful iterations producing outputs that the AI expects.

Primary tools & libs
- ffmpeg (command-line) — decode/inspect MP4, extract frames/audio
- libav* (optional) or spawn ffmpeg from C++ for decoding
- d2x-xl / MVE/MVL spec references (docs, reverse-engineered notes)
- Local test player: ffplay / d2x-xl local build

Constraints & rules
- No proprietary game assets in repo or commits.
- Do not use tools that intentionally bypass DRM.
- Keep work incremental and test-driven when possible.

Where to find help
- PROMPTS.md — effective prompts and templates (use these so AI sees consistent wording)
- LEARNING_JOURNAL.md — record what you tried, what you learned, and what to try next
