# meteserpil.pages.dev

My personal site — a single static page, no build step.

**Live:** [meteserpil.pages.dev](https://meteserpil.pages.dev)

## What's here

| File | What it is |
|---|---|
| `index.html` | The whole site: markup, CSS and JS in one file, with the portrait embedded as a data URI |
| `cv.pdf` | The CV the download buttons serve |

## Running it locally

There is nothing to compile. Serve the folder over HTTP so the CV download works:

```bash
npx serve
# or
python3 -m http.server 8000
```

Opening `index.html` by double-clicking also works, but browsers block the
`download` attribute on `file://`, so the CV buttons do nothing that way.

## Notes

- Light and dark themes follow the system setting, with a toggle in the header that remembers the choice per browser.
- The Database section renders the CV as interactive psql-style tables — click a table to query it, then a row to expand the record.
- Responsive from 375px to 2560px; the header wraps below 1000px.
- The scrolling tech strip has a pause control and stops entirely under `prefers-reduced-motion`.

## Deploying

Cloudflare Pages builds from this repo on every push to `main`: no build command, output directory `/`.
