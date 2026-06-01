# Agent Instructions

This repository contains a reusable scene-view rotation skill. When a user asks to generate alternate views from a reference scene image, read and follow `SKILL.md`.

## Core Behavior

- Treat the uploaded image as the 0-degree baseline.
- Use image editing or reference-image generation when available.
- Generate 90-degree, 180-degree, and 270-degree horizontal camera rotations unless the user requests fewer.
- Preserve the same indoor or outdoor place, spatial layout, lighting, materials, atmosphere, aspect ratio, and realistic photographic style.
- Do not redesign the scene or turn it into a different location.

## Agent Compatibility

- Codex-style agents can use this repository directly through `SKILL.md` or `AGENTS.md`.
- Claude Code can install `SKILL.md` as a skill under `~/.claude/skills/scene-view-rotation/SKILL.md` or `.claude/skills/scene-view-rotation/SKILL.md`.
- Agents without a skill system can use `UNIVERSAL_PROMPT.md` as a copy-paste prompt template.
