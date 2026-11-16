# ExamForge – Multi-Subject Study & Exam Simulator Guide

## A. How to Replace Your Old GitHub Pages Project
1. **Extract the ZIP**: Unzip `ExamForge-upgraded.zip` on your phone (using *Files by Google* → Extract) or computer. You will see 7 files:
   - `index.html`
   - `manifest.json`
   - `service-worker.js`
   - `questions.json`
   - `icon-192.png`
   - `icon-512.png`
   - `GUIDE.md`
2. **Open Your GitHub Repository**: Go to `github.com` and open your existing `examforge` repository.
3. **Upload & Overwrite Files**:
   - Tap **Add file** → **Upload files**.
   - Select **all 7 files** from the extracted folder and drag/upload them into the repository root (`/`). GitHub will automatically overwrite the old versions of `index.html`, `service-worker.js`, `manifest.json`, `questions.json`, and `GUIDE.md`.
   - Tap **Commit changes**.
4. **Refresh Your Installed PWA**:
   - Because `service-worker.js` was updated from `examforge-v2` to `examforge-v3`, open your GitHub Pages URL (`https://YOURNAME.github.io/examforge/`) while online and refresh the page once. The new version will cache automatically for offline use.

---

## B. Multi-Subject Kisi-Kisi JSON Format
ExamForge supports **grouped multi-subject JSON files**, **flat per-question subject labels**, and **legacy single-subject files**:

```json
{
  "title": "ASAS Day 2 Kelas X",
  "duration": 120,
  "subjects": [
    {
      "name": "Pendidikan Pancasila",
      "duration": 40,
      "questions": [
        {
          "id": 1,
          "type": "multiple_choice",
          "question": "Question text...",
          "options": { "A": "...", "B": "...", "C": "...", "D": "...", "E": "..." },
          "answer": "C",
          "points": 10,
          "explanation": "Explanation..."
        }
      ]
    },
    {
      "name": "Bahasa Inggris",
      "questions": []
    },
    {
      "name": "Olah Raga (PJOK)",
      "questions": []
    }
  ]
}
```
*Note: If a file mentions multiple subjects without identifying which question belongs to which subject, ExamForge will safely reject it and display a helpful explanation.*

---

## C. New Student Features
- **Subject Cards Dashboard**: Each subject gets its own color-coded card with an icon, question count, best score progress bar, and dedicated **Start Examination** flow.
- **Subject-Filtered History**: Filter your past exam results by individual subject or view all attempts together.
- **Study Music & Sound Effects (🎵)**:
  - Tap the **🎵** button in the top bar to open the Audio Studio.
  - Play the built-in Web Audio ambient piano loop or tap **Upload Music** to play your own `.mp3`, `.wav`, or `.ogg` study track from your device.
  - Toggle interface sound effects (clicks, answer selection, navigation, completion fanfare), adjust volume, or mute all audio. Preferences persist in `localStorage`.
- **Bilingual Support (🌐 EN / ID)**: Tap the language button in the top header to switch instantly between English and Bahasa Indonesia.
