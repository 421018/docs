# 42 Chain documentation

The texts of the documentation published at [42chain.org/docs](https://42chain.org/docs):
how Infinite Drive works and how to connect, build, integrate systems and run a
node. Plain Markdown, in English and Spanish, with no code: the site
(the `site` repository) turns it into pages, widgets and diagrams.

## Layout

| Path | What it holds |
|---|---|
| `<lang>/home.md` | The documentation's home (the developers' home): title, routes by goal, the console block, live panel texts. |
| `<lang>/pages/<section>/index.md` | A section: its label, order and index page. |
| `<lang>/pages/<section>/<page>.md` | A page of that section. |
| `<lang>/diagrams/` | Diagrams used with the `:::diagram` block; a language without one uses the Spanish file. |

`es/` is written first; `en/` follows. A page missing in English shows the
Spanish one with a notice. Folder and file names are English: they are the
public addresses (`pages/protocol/fees.md` → `/docs/protocol/fees`).

What stays in the site, not here: the documentation's header, notice and
search texts (the `site` repository, `apps/web/content/docs-ui/`), and the
network data used by the network widgets (the `network` repository).

## Writing

- Front matter and `:::` blocks follow the schemas in the `site` repository
  (`apps/web/src/kit/schemas.ts`, `apps/web/src/content.config.ts`); a
  misspelled field or an unknown block stops the build and the check names it.
- Widgets are inserted with `:::widget{name="…"}`; no HTML, MDX or scripts.
- Links to other docs pages are written without language or area:
  `/protocol/consensus`. `site:/…` and `console:/…` point to the other areas.
- Before stating a protocol figure, read it from the chain.

## Seeing a change locally

This repository has nothing to run on its own. Use the site, with this
repository as its `apps/web/content/docs` submodule:

```bash
git clone --recurse-submodules https://github.com/<org>/site.git
cd site && npm ci && npm run dev   # http://localhost:4321/docs
```

Edit the files under `apps/web/content/docs/` (they are this repository), then
commit and push from that folder. `npm run verify` in the site checks
everything before you open a pull request.

## How a change is published

1. A pull request runs **Check** (`.github/workflows/check.yml`): it builds the
   whole site with the change and checks every internal link and anchor.
2. Merging into `main` runs **Publish** (`.github/workflows/publish.yml`): it
   calls the Cloudflare Pages deploy hook of 42chain.org, whose build takes the
   `main` of every content repository. The change is live a few minutes later.

Setup, once: in the site's Pages project, **Settings → Builds → Add deploy
hook** (branch `main`), and save its URL in this repository as the Actions
secret `CF_DEPLOY_HOOK`. Treat it as a secret: anyone with the URL can start a
build.

## License

Texts and diagrams under [CC BY 4.0](LICENSE). © The 42 Chain contributors.
