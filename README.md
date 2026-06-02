# FormForge

**Build forms. Upload documents. Let AI fill the gaps.**

FormForge is an AI-powered form builder and document autofill tool. Define a custom form schema, upload a PDF or image, and Claude automatically extracts and populates matching field values. Review, edit, and export the result — no server required.

---

## Quick Start

1. Open `index.html` in any modern browser (Chrome, Firefox, Safari, Edge).
2. No installation, no build step, no server needed.

---

## How to Use

### Step 1 — Build Your Form

- Pick one of the three built-in templates (Job Application, Invoice, Medical Intake), or
- Add fields manually using the **Add Field** form at the bottom.
- Supported field types: **text**, **textarea**, **number**, **date**, **dropdown**, **checkbox**.
- Mark fields as **Required** to enforce them at save time.
- Remove any field with the ✕ button.

### Step 2 — Upload & Extract

- Enter your **Anthropic API key** (stored in your browser session only — never sent anywhere except the Anthropic API).
- Drag-and-drop or browse to upload your document.
- Supported formats: **PDF**, **PNG**, **JPG**, **JPEG** — up to **10 MB**.
- Click **Extract with AI** — Claude reads the document and populates the form fields automatically.

### Step 3 — Review & Save

- **Green fields** were filled by AI.
- **Amber fields** are required but were not found in the document — fill them in manually.
- All fields are fully editable.
- **Save Form** — validates that all required fields are filled.
- **Download JSON** — saves `form-data.json` to your computer.
- **Copy as JSON** — copies `{ "Field Label": "value", … }` to the clipboard.
- **Start Over** — resets everything to begin a new form.

---

## Getting an API Key

1. Go to [console.anthropic.com](https://console.anthropic.com).
2. Sign in or create an account.
3. Navigate to **API Keys** and create a new key.
4. Paste it into the **API Key** field in Step 2.

The key variable used in this project is `NIA_API_KEY`.

> **Security note:** This app calls the Anthropic API directly from your browser. Your API key is held in memory only for the current session and is never stored on disk or sent to any server other than `api.anthropic.com`. For production use, proxy the API call through a backend server.

---

## Built-in Templates

| Template        | Fields |
|-----------------|--------|
| Job Application | Full Name, Email, Phone, Position, Skills, Years of Experience, Start Date, Employment Type |
| Invoice         | Invoice Number, Date, Vendor, Client, Description, Amount, Tax, Status |
| Medical Intake  | Patient Name, Date of Birth, Gender, Phone, Emergency Contact, Allergies, Current Medications |

---

## Supported Field Types

| Type       | Description                        |
|------------|------------------------------------|
| text       | Single-line text input             |
| textarea   | Multi-line text input              |
| number     | Numeric input                      |
| date       | Date picker (YYYY-MM-DD)           |
| dropdown   | Select from a list of options      |
| checkbox   | Boolean toggle (true / false)      |

---

## File Structure

```
FormForge/
├── index.html   — the complete application (open this in a browser)
├── PROMPT.md    — system prompt used by the AI extraction engine
├── CLAUDE.md    — developer spec and API configuration reference
└── README.md    — this file
```

---

## Technical Notes

- **No dependencies** — vanilla HTML, CSS, and JavaScript only.
- **Model** — `claude-sonnet-4-20250514` via the Anthropic Messages API.
- **PDF support** — uses the `anthropic-beta: pdfs-2024-09-25` header automatically.
- **API key variable** — `NIA_API_KEY` (see `CLAUDE.md` for full API specification).

---

*Powered by [Anthropic Claude](https://anthropic.com).*
