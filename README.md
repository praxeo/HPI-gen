# ED HPI Generator

Fast, accurate, and complaint-driven HPI creation for Emergency Department clinicians and scribes.

## What is it?

A single-page, zero-dependency web application that guides users through 5-8 clicks to generate a complete, well-structured History of Present Illness paragraph ready for pasting into any EMR. Built for physicians, NPs, PAs, and scribes who need consistency and speed without sacrificing detail.

## Key Features

- **Complaint Library**: 15+ chief complaints including Chest pain, Laceration, MVC, Stroke-like, Pregnancy-related, GU, Injury, and more
- **Smart Prompts**: Questions adapt to the complaint (e.g., "LOC?" for MVC, "Vaginal bleeding?" for pregnancy)
- **Auto-HPI**: Generates publication-ready paragraph with onset, duration, character, severity, radiation, context, modifying factors, associated symptoms, PMH, meds, surgeries
- **Copy-to-Clipboard**: One-click copy with no formatting headaches
- **AI Refinement Demo**: One-click placeholder for future NLP polish
- **Progress Log**: Visual breadcrumb trail of answers entered
- **Responsive & Fast**: Works on phones, tablets, desktops; loads in under 200ms
- **Zero Backend**: Pure HTML/CSS/JS—host anywhere (Vercel, Netlify, GitHub Pages, SharePoint, local file)

## How to Use

1. Open `index.html` in any browser
2. Tap "Start HPI Generator"
3. Pick a chief complaint (or choose "Other")
4. Answer the step-by-step prompts (onset, location, character, severity, context, modifiers, associated sx, history)
5. Copy the finished HPI to your EMR
6. Tap "Generate Another" to repeat

## Example Output

**Motor Vehicle Collision:**
MVC occurred 45 minutes ago. The patient was the restrained driver. Airbags deployed. Complains of midsternal chest pain (8/10) and left wrist pain. Denies LOC, nausea, or dyspnea. Symptoms worsen with deep inspiration and movement. No prior similar episodes. PMH: HTN, DM2. Meds: Lisinopril, Metformin. Surgical history: Appendectomy.

## Tech Stack

- HTML5 semantic markup
- CSS3 with CSS variables for theming
- Vanilla ES6 JavaScript (no frameworks)
- Flexbox/Grid for responsive layout
- Web Clipboard API for copy-to-clipboard

## Adding New Complaints

1. Open `index.html`
2. Find the `<div class="cc-grid">` block
3. Duplicate any line:
   ```html
   <div class="cc-option" onclick="selectChiefComplaint(this, 'Your New Complaint')">Your New Complaint</div>
   ```
4. Save and refresh—done!

## Deploy in 30 Seconds

### Vercel (recommended)
```bash
npm i -g vercel  # one-time install
vercel --prod    # drag-and-drop the folder
```

### GitHub Pages
1. Fork/clone this repo
2. Enable Pages in repo settings → source = main branch
3. Visit `https://yourname.github.io/ed-hpi-generator`

### Local Use (no server)
```bash
# macOS/Linux
python3 -m http.server 8000
# Windows
start index.html  # double-click
```

## License

MIT – do whatever you want, just don't sue us.

## Disclaimer

This tool is for educational and documentation-assistance purposes only. It does not replace clinical judgment. Always review and edit the generated text before signing your note.

## Contribute

Issues and PRs welcome! Feature ideas: pediatric complaints, procedure notes, discharge instructions, vitals auto-import.
