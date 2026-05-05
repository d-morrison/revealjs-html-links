# revealjs-html-links

A [Quarto](https://quarto.org/) extension that adds a persistent
**"Webpage version"** button to RevealJS presentations, linking back to the
corresponding HTML notes document and updating the anchor as slides change.

## Installation

```bash
quarto add d-morrison/revealjs-html-links
```

This installs the extension into `_extensions/d-morrison/revealjs-html-links/`
in your Quarto project.

## Usage

Add the extension as a filter in your document or project configuration:

```yaml
filters:
  - d-morrison/revealjs-html-links
```

The extension is a no-op for non-RevealJS formats, so it is safe to include
in a project that produces both slides (`-slides.html`) and HTML notes.

### URL convention

The button only appears when the presentation URL ends with `-slides.html`.
In that case it strips the `-slides` suffix to construct the base URL of the
notes document, e.g.:

| Slides URL | Notes URL |
|---|---|
| `my-talk-slides.html` | `my-talk.html` |
| `my-talk-slides.html#slide-two` | `my-talk.html#slide-two` |

The anchor fragment is kept in sync with the current slide via the
Reveal.js `slidechanged` event.

## Example

See [`example.qmd`](example.qmd) for a minimal demonstration.