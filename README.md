# arpon

Talk like smart caveman. Same brain, fewer tokens.

## What it does

Compress every model response to arpon-style prose. Drops articles, filler, pleasantries, hedging. Keeps every technical detail, code block, error string, and symbol exact. Cuts ~65–75% output tokens while preserving full accuracy. Mode persists for the whole session until changed or stopped.

Three intensity levels:

| Level | What changes |
| ------ | ------------ |
| `lite` | Drop filler and hedging. Keep full sentences. Professional but tight. |
| `full` | **Default.** Drop articles. Fragments OK. Use shorter synonyms. |
| `ultra` | Bare fragments. Abbreviations (`DB`, `auth`, `fn`). Use arrows (`→`) for causality. |

## Auto-clarity

arpon temporarily switches back to normal prose for:

- Security warnings
- Irreversible action confirmations
- Multi-step instructions where fragment ambiguity could cause mistakes
- Repeated questions

After the clear section, arpon resumes automatically.

## Commands

```text
/arpon              # full mode (default)
/arpon lite         # lighter compression
/arpon ultra        # extreme compression
stop arpon          # back to normal prose
```

## Setup

1. Download this repository as a **ZIP**.
2. Open **Claude**.
3. Go to **Customize**.
4. Click **Add Skill**.
5. Click **Create Skill**.
6. Click **Upload Skill**.
6. Drag and drop the zip file into Claude.

Done. arpon is now available in every chat.

## Example

**Question**

> Why does my React component re-render?

**Normal**

> Your component re-renders because you create a new object reference each render. Wrapping it in `useMemo` will fix the issue.

**arpon (`full`)**

> New object ref each render. Inline object prop = new ref = re-render. Wrap in `useMemo`.

**arpon (`ultra`)**

> Inline obj prop → new ref → re-render. `useMemo`.

## See also

- `SKILL.md` — Full LLM-facing instructions.