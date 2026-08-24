# policies

Privacy policies for every published app, one folder each, served by GitHub
Pages. Play requires a public policy URL per listing and will not accept a
listing without one; this repo is where those URLs live so they outlast any
free-tier host.

> **This repo is public.** GitHub Pages needs it to be. Nothing but policy
> pages goes in here — never a keystore, a key password, a service-account
> JSON or an API key. `_shared/keystores/` sits next to this folder on disk;
> keep it there.

## URLs

Once Pages is switched on, each folder is served at its own address:

```
https://<username>.github.io/Policies/            → this index
https://<username>.github.io/Policies/pagenova/   → PageNova
```

> **The path is case-sensitive.** The repo is named `Policies`, so the live
> address is `https://ramdasgat.github.io/Policies/` with a capital P.
> `.../policies/` returns 404. Paste the wrong case into Play Console and the
> reviewer sees a dead link, which is a rejection.

Substitute your GitHub username. The URL is stable as long as the repo and the
folder name stay put — so once one is pasted into a Play listing, do not rename
the folder.

## Turning Pages on (once)

1. Push this folder to a **public** repo named `policies`.
2. Repo → **Settings** → **Pages**.
3. Source: **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Wait about a minute, then load the URL above in a private window. No
   sign-in wall — that is Play's actual requirement, and the thing to verify.

## Adding an app

1. `mkdir <appname>` and put its policy in it as `index.html`. The filename
   matters: `index.html` is what makes the folder itself a working URL.
2. Add a row to the list in the root `index.html`.
3. Commit and push. Pages redeploys on its own.

## Updating a policy

Edit the file in place and push. The address stays the same, which is what the
policies themselves promise ("the updated version replaces this one at the same
address"). Change the `Last updated` date at the top of the page in the same
commit.

Never publish a changed policy at a new URL — the old one is already in a live
Play listing and in the app.

## Where each policy comes from

| Folder | App | Source of truth |
|---|---|---|
| `pagenova/` | PageNova (`com.ramdas.pagenova`) | `LitePdfReader/playstore/privacy-policy.md`, rendered to `privacy-policy.html` |
| _(its own repo)_ | ChaarPaisa (`com.chaarpaisa`) | `ChaarPaisa/Playstore/privacy-policy/privacy-policy.md`, published to the standalone `chaarpaisa-privacy` repo |

The app repo holds the markdown the policy is written in; the HTML here is the
published form of it. If a policy changes, change it in the app repo too, so
the two do not drift.

## `.nojekyll`

Present so GitHub serves the files exactly as they are, instead of running them
through Jekyll. Nothing here needs Jekyll, and it would ignore any file or
folder starting with an underscore.
