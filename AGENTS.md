# Video Use — Agent Rules

This repository is Carson's dedicated video-production project and the canonical
home of its project-local skills. Do not install or fan these skills out from the
global `~/.agents` fleet.

## Skill routing

- For conversational video editing, read the complete root `SKILL.md` before
  acting. Its hard production-correctness rules and approval boundary apply.
- For a Manim animation or a Manim slot within an edit, also read the complete
  `skills/manim-video/SKILL.md` and only the references it routes to.
- `.agents/skills/` contains thin project adapters that route to those canonical
  sources. `.claude/skills/` is a project-local symlink fan-out to the adapters.
  Do not duplicate the upstream instructions in either location.

## Project boundaries

- Source footage stays outside this repository. All session output belongs in
  `<videos_dir>/edit/`; never write footage, transcripts, renders, or project
  memory into this checkout.
- Keep source files untouched. A plain-English editing strategy requires user
  confirmation before modifying the cut.
- Never expose or commit `.env` values. Ask for a missing ElevenLabs key only
  when a video task requires transcription.
- Preserve the upstream skill and helper layout. Make local skill wiring changes
  in `.agents/skills/` and `.claude/skills/`; change the upstream skill content
  only when the user explicitly asks to maintain or fork it.

## Verification

Use the checks required by the selected skill. At minimum, validate edited
Python with the project environment, inspect rendered media with `ffprobe`, and
complete the root skill's bounded self-evaluation before presenting output.
