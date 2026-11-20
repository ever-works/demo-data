# demo-data — content of the directory template's demo

Data repository of the **directory-web-template demo deployment** of
[Ever Works](https://ever.works) (Kubernetes namespaces `ever-works-demo-*`).
That deployment used to serve https://demo.ever.works. The address now
belongs to the **Ever Works platform demo** (a private sandbox of the
platform itself), and the template's live example is
**https://dir.ever.works**, a directory the platform built from the
template.

> ⚠️ **Every listing in this repository is FICTIONAL.** The products and
> companies described here do not exist. Nothing in `data/` is a review of, or a
> claim about, any real product or organisation. It exists purely so the demo
> site has realistic-looking content to render.

## Layout

| Path | Purpose |
| --- | --- |
| `.works/works.yml` | Site config — `company_name` (drives the `<title>`), hero copy, `auth.credentials`, monetization |
| `categories.yml` / `tags.yml` | The taxonomy the listings reference |
| `data/<slug>/<slug>.yml` | One listing: name, description, category, tags, `markdown` body |
| `data/<slug>/<slug>.md` | The same body as a standalone markdown file |
| `pages/*.en.md` | About + the Terms / Privacy / Cookies pages the footer links to |

## Adding a demo listing

Create `data/<slug>/<slug>.yml` (+ a matching `.md`), using an existing entry as
the template. `category` must match a `name` in `categories.yml`; each tag must
match an `id` in `tags.yml`. Keep new entries clearly fictional.

The template demo deployment clones this repo at runtime, so changes appear
after its pods restart. It is scaled to 0 since the platform demo took over
demo.ever.works; it is kept, not deleted, and can be scaled back up.
