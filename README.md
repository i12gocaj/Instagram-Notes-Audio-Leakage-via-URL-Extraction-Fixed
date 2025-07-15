# 🎙️ Instagram Notes Audio Leakage via URL Extraction (Fixed & Rewarded)

🛡️ Vulnerability Summary

In [05/2025], I discovered a vulnerability in Instagram Web that allowed any user to extract the **original video file** from a Note and access the **background audio**, which was not meant to be publicly available. This bypassed the privacy model of the Notes feature, where videos are supposed to be displayed silently.

⚠️ This vulnerability has been **responsibly disclosed, validated, and fixed**.
I reported it to Meta via their Bug Bounty Program and was awarded **$1000** for this finding.
**Case ID:** `3950957211809485`

The root cause was traced to the data sanitization process used when uploading
video Notes on certain server nodes. On U.S. servers the vulnerability did not
appear, making it difficult for Meta's engineers to reproduce the issue at
first.

🔍 Impact

By inspecting the element and copying the direct video URL, any user could retrieve the original video — **including audio** — even though Instagram Notes are designed to suppress audio playback. This exposed private conversations, ambient sounds, or unintended background content uploaded by the user.

🧪 Proof of Concept

📹 Video: `instagram_notes_audio_leakage.mov`

Steps:
1. Open Instagram Web and view any video Note.
2. Open browser DevTools (Right-click > Inspect).
3. Locate the `<video>` or `<source>` tag and copy the `src` URL.
4. Paste the URL in a new tab.
5. The original video plays **with full audio**, bypassing the frontend's muted design.

📄 Responsible Disclosure

Meta acknowledged and validated the issue, awarding a **$1000 bounty** as part of their bug bounty program. The issue has since been silently patched.

👨‍💻 Author

**Javier González Casares**  
Cybersecurity & Software Engineering
