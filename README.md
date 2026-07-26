# Practice Dashboard

A self-contained practice dashboard covering IT fundamentals, networking, operating systems, scripting, and security. Single HTML file — no build step, no dependencies beyond a browser.

**[Open the dashboard](https://r7d2jzv2g8-dot.github.io/it_prep/)** 

---

## What it covers

- **154+ fixed practice questions** across four sections (Networking, OS, Security, Fundamentals), plus **unlimited procedural content** in Scripting (10 code-tracing generators) and Networking (subnetting, and realistic generated `netstat`/`ip route`/`iptables`/`nmap`/`ps aux` output).
- **Weak-spot tracking** at the individual topic level — not just section-wide — with a dedicated card showing exactly which topics need work and one-tap practice for any of them.
- **Custom topic picker** — build a session from any mix of specific topics across any section, not just whole-section or weak-topic practice.
- **Section strength tiles**, a running correct/incorrect tally during each session, and a mid-session exit that doesn't lose progress already made.
- **Pomodoro timer** with configurable focus/break durations, and an exam-day countdown.

## Files it depends on

The dashboard's "Reference materials" section links to these files by relative path — they need to sit in the same folder as `practice_dashboard.html` for those links to resolve once hosted:

```
practice_dashboard.html
practice-manifest.json
practice-service-worker.js
practice-icon-192.png
practice-icon-512.png
diagnostic_exam.html
Final-Exam-Prep-Guide.pdf
Cheat-Sheet-1-Fundamentals-Networking.pdf
Cheat-Sheet-2-Linux-Unix.pdf
Cheat-Sheet-3-Windows.pdf
Cheat-Sheet-4-Scripting.pdf
Cheat-Sheet-5-Security.pdf
Cheat-Sheet-6-Forensics.pdf
```

If any of these are missing, the dashboard itself still works fully — only the reference links under that section will 404. The PWA files (`practice-manifest.json`, `practice-service-worker.js`, and the two icon PNGs) are needed specifically for "Add to Home Screen" and offline access to work — the dashboard's core functionality doesn't depend on them.

## Progress data

Section scores, per-topic weak-spot tracking, and Pomodoro settings are all stored in the browser via `localStorage`, scoped to wherever the file is hosted. On GitHub Pages, that means progress persists reliably across visits to the same URL, unlike opening a local file directly, where storage can behave inconsistently depending on how the file was saved or reopened.

**If you're replacing an existing, already-in-use version of this dashboard hosted at the same URL:** the storage keys were recently renamed as part of removing exam-specific references from the code. The dashboard automatically migrates any progress saved under the old key names the first time it loads after this update — nothing to do on your end, and no progress should be lost, but it's worth confirming your weak-spot data still looks right after the first load post-update.

---

## Hosting on GitHub Pages — step by step

This uses GitHub's website only — no command line or git installation needed.

### 1. Create a GitHub account (skip if you already have one)
Go to [github.com](https://github.com) and sign up. It's free.

### 2. Create a new repository
1. Click the **+** icon in the top-right corner → **New repository**.
2. Give it a name, e.g. `practice-dashboard` (no spaces — use hyphens).
3. Set it to **Public** (required for free GitHub Pages hosting).
4. Leave everything else at its default, and click **Create repository**.

### 3. Upload the files
1. On your new repository's page, click **Add file → Upload files**.
2. Drag in every file listed above under "Files it depends on."
3. Scroll down and click **Commit changes**.

*(GitHub's upload page accepts multiple files at once — you don't need to do this one at a time. If you ever need to update a file later, use the same **Add file → Upload files** flow; uploading a file with the same name overwrites the old version.)*

### 4. Turn on GitHub Pages
1. In your repository, click **Settings** (top menu bar).
2. In the left sidebar, click **Pages**.
3. Under "Build and deployment," for **Source**, select **Deploy from a branch**.
4. Under "Branch," select **main** and **/ (root)**, then click **Save**.
5. Wait a minute or two — GitHub will show a message with your live URL once it's ready, in the form:
   `https://yourusername.github.io/practice-dashboard/`

### 5. Find your dashboard
It's now live at:
`https://yourusername.github.io/practice-dashboard/practice_dashboard.html`

(Replace `yourusername` and `practice-dashboard` with your actual GitHub username and whatever you named the repository.)

### 6. Bookmark it, or add it to your phone's home screen
Once live over HTTPS, the dashboard supports "Add to Home Screen" on mobile for offline access — open the URL in your phone's browser, then use the browser's share/menu button to add it.

---

*No API keys, no backend, no build process — everything runs entirely in the browser.*
