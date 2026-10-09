Art Motion proof of concept for My Hero Movie.

Purpose: test code-driven Canvas animation as an isolated layer without changing the production pipeline.

Run: open index.html in a modern browser. The prototype should allow a local drawing to be selected and composed into an animated scene. No API key or remote upload should be required.

Limit: this spike does not split drawings into independently animated limbs or generate new character poses. Compare a browser Canvas baseline with a small upstream Huashu Art Motion render before deciding whether to integrate.

Upstream: https://github.com/alchaincyf/huashu-art-motion

Acceptance: local run, drawing upload, responsive motion, no network requirement, and measured quality/setup time against Remotion and FFmpeg.