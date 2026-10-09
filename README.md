# My Hero Movie

Turn a child's own drawing into the hero of their own story.

## MVP

This first prototype is intentionally dependency-free:

1. Upload a child's drawing.
2. Name the hero.
3. Choose an adventure.
4. Animate the drawing in the browser.
5. Generate a short movie moment.
6. Let the hero speak using the browser's speech synthesis.

## Product direction

The long-term product is a child-first creation experience:

DRAW -> BECOME -> ADVENTURE -> MOVIE

The animation backend is intentionally replaceable. Candidate OSS engines include Mesh Avatar Studio and Stretchy Studio.

## Run locally

Open index.html directly, or run run.bat on Windows.

## Important

This is an early validation prototype. It is designed to test whether children find the experience magical before we invest in a full generative-video pipeline.

## Art Motion integration

The browser prototype now includes a lightweight, dependency-free Art Motion-inspired animation layer:

- **35 selectable art treatments** for the child's uploaded drawing and the surrounding scene.
- Style-aware colours, filters, animated motifs, and a mesh-warp animation of the original drawing.
- **8-second WebM export** using the browser's Canvas capture and MediaRecorder APIs. Chrome and Edge are recommended; support depends on the browser.
- No paid API, external video service, or additional runtime package is required for this MVP.

Reference project: [alchaincyf/huashu-art-motion](https://github.com/alchaincyf/huashu-art-motion). This is a browser-native adapter inspired by its approach, not a bundled copy of its Python/Playwright/FFmpeg renderer. The upstream project uses MIT-licensed code and documentation, with separate license terms for its bundled fonts, stroke data, and demo character artwork. No upstream demo character artwork is included here.

### Current export boundary

The exported clip contains the animated canvas, selected story title, and narration text. Browser speech synthesis plays during recording where supported, but the browser's spoken audio is not mixed into the WebM yet. Full, frame-accurate rendering and audio-mixed MP4 generation can be added later by connecting the upstream render pipeline to a server-side job.

