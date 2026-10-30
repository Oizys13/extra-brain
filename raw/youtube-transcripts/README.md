# raw/youtube-transcripts/ — YouTube transcripts

Raw captions/transcripts from videos you want to keep. Plain text, unedited — readability
cleanup and summaries belong in `wiki/`.

**What belongs here**

- Auto-generated or manually uploaded captions exported as `.txt`, `.srt`, or `.vtt`.
- One file per video.

**Naming convention (recommended)**

`YYYY-<channel-slug>-<video-title-slug>.txt`, e.g.
`2025-lex-fridman-andrej-karpathy-agi.txt`

If a video has no title/date yet, use the video ID: `<video-id>.txt`
(the part after `v=` in the URL, e.g. `dQw4w9WgXcQ`).

**Where to export it from**

- **Built-in:** open the video → **...more** under the description → **Show transcript** →
  copy into a text file.
- **YouTube Studio** (for your own videos): Subtitles → download `.srt`/`.vtt`.
- **Third-party tools:** browser extensions like "YouTube Transcript", or CLI tools such as
  `yt-dlp --write-auto-subs --skip-download <url>`.

Add a first-line header in each file with the video URL, channel, and publish date so the
source is always recoverable.
