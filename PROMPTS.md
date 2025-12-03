# Prompt Templates and Examples

Why: reuse the same structured prompts so Copilot/Chat gets useful, consistent input.

General bug-fix prompt (paste exact compiler/runtime output)
- "Context: project is a C++ tool to convert MP4→MVE. Relevant files: src/main.cpp, src/encoder.cpp. Build command: g++ -std=c++17 -O2 -o bin/tool src/*.cpp. I ran the build and got these errors: [paste compiler output]. Please identify the minimal fix for the code, explain why it fails, and provide the patched file(s). Keep changes minimal and explain any new includes or library requirements."

Feature-request prompt
- "Add a function to decode a single frame from MP4 using ffmpeg command-line (not libav). The function should call ffmpeg to extract frame N as a PNG into /tmp and return the filepath. Provide robust error handling and a short unit-test that checks frame 0 exists."

Test/failure explanation prompt
- "I ran the tool with input test.mp4 and ffplay shows the output is 2 frames shorter than the original. Here is the console output and a hex dump of the first 512 bytes of the generated MVE: [paste]. Explain likely causes and suggest targeted fixes."

Update project brief prompt
- "Update CONTEXT.md to reflect these changes: added encoder.cpp and tests/test_basic.sh; fixed frame-timing bug. Keep it to 4–6 lines and set status to 'alpha — local use only'."

How to paste outputs
- Always include:
  - exact command(s) you ran
  - full compiler error messages
  - relevant small file snippets (not entire repo)
  - environment info (OS, compiler version, ffmpeg version)

Privacy note
- Do not paste secrets or proprietary content (game MP4s). Redact any sensitive file contents.
