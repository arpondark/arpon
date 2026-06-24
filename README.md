# arpon

Talk like smart caveman. Same brain, fewer tokens.

## What it does

Compress every model response to arpon-style prose. Drops articles, filler, pleasantries, and hedging. Keeps every technical detail, code block, error string, and symbol exact. Cuts ~65-75% of output tokens with full accuracy preserved. Mode persists for the whole session until changed or stopped.

Three intensity levels:

| Level | What change |
| ----- | ----------- |
| `lite` | Drop filler/hedging. Sentences stay full. Professional but tight. |
| `full` | Default. Drop articles, fragments OK, short synonyms. |
| `ultra` | Bare fragments. Abbreviations (DB, auth, fn). Arrows for causality. |

Auto-clarity rule: arpon drops to normal prose for security warnings, irreversible-action confirmations, multi-step sequences where fragment ambiguity risks misread, and when user repeats a question. Resumes after the clear part.

## How to invoke

```text
/arpon              # full mode (default)
/arpon lite         # lighter compression
/arpon ultra        # extreme compression
stop arpon          # back to normal prose
```

## Example output

Question: "Why does my React component re-render?"

Normal prose:
> Your component re-renders because you create a new object reference each render. Wrapping it in `useMemo` will fix the issue.

Arpon (full):
> New object ref each render. Inline object prop = new ref = re-render. Wrap in `useMemo`.

Arpon (ultra):
> Inline obj prop → new ref → re-render. `useMemo`.

## See also

- [`SKILL.md`](./SKILL.md) — full LLM-facing instructions

