# demo-data — content for demo.ever.works

Data repository behind **https://demo.ever.works**, the public demo of the
[Ever Works](https://ever.works) directory platform.

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

The deployed site clones this repo at runtime, so changes appear after the demo
pods restart.
