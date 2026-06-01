# Claude Instructions

Use `SKILL.md` as the authoritative instruction file for this scene-view rotation skill.

When the user provides a scene image and asks for alternate directions, reverse angles, left/right views, orbit/turnaround views, or 90/180/270-degree views:

1. Treat the uploaded image as the 0-degree baseline.
2. Prefer image editing or reference-image generation that can use the uploaded image.
3. Generate the requested horizontal camera rotation views.
4. Preserve the same indoor or outdoor environment, lighting, materials, atmosphere, aspect ratio, and realistic photographic style.
5. Avoid redesigning the scene, changing weather/time/season, or inventing inconsistent objects.

For Claude Code skill installation, place this repository or its `SKILL.md` file at:

```text
~/.claude/skills/scene-view-rotation/SKILL.md
```

For project-local use, place it at:

```text
.claude/skills/scene-view-rotation/SKILL.md
```
