# Viral Material Library Workflow

## Principle

```text
你喂为主，我找为辅。
```

Use this workflow when the user provides a video link, local video file, screenshot, title/caption, performance data, or asks to find and analyze public viral references.

## Source Modes

### User-fed

The user provides one or more of:

- video link
- local video file
- screenshot
- title/caption
- performance data
- notes about why the video is interesting

This is the preferred mode because it reflects what the user actually notices in the wild.

### Assistant-found

Use only when the user asks to find references. Search public sources and be honest about platform limits. Do not claim complete coverage of Douyin or 视频号 feeds.

## Output

Each item should become one Markdown file under:

```text
爆款拆解库/
  抖音/
  视频号/
  小红书/
  通用结构/
```

Use `templates/viral-breakdown-template.md`.

## Analysis Steps

1. Identify platform and source.
2. Extract the first 3 seconds hook.
3. Identify the core conflict or promise.
4. Map the口播 structure.
5. Note visual structure: talking head, picture-in-picture, screen recording, B-roll, text card.
6. Note subtitle rhythm and emphasis words.
7. Extract title/cover/comment strategy.
8. Explain why it may work.
9. Rewrite as a 老初 / AI 装机师 version.
10. Suggest 3-5 follow-up videos.

## Reuse

When producing a new video concept, retrieve 1-3 relevant breakdowns first if the user asks to use the library. Adapt structures, not wording.
