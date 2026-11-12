# Maps of Meaning Wiki — Jordan Peterson's "Two Ways of Looking at the World"

A plain-language study guide to **Jordan B. Peterson's** Maps of Meaning lecture series, *Two Ways of Looking at the World*.

**Public copy:** https://iamflipse.github.io/maps-of-meaning-wiki/ (read-only; static build served from the `gh-pages` branch)

## Contents

- **54 section pages** in lecture order, grouped into 11 parts, from the frame of perception to the tree of life and the prayer of humility. Each has a summary and key ideas (paraphrase), 2–4 short exact quotes (under ~30 words), questions to explore and related links.
- **40 concept pages** (aim, order and chaos, conscience, sacrifice, the hero, the brazen serpent...) with quotes and the sections where each idea appears.
- **Study aids:** cheat sheet, themes index (search words mapped to concepts and sections), all section quotes, and a coverage map of transcript word ranges.
- **Sources:** distilled from a private ~98.8k-word transcript of the lectures; the transcript itself is not published. See `src/about.md`.
- **Companion:** [Sermon on the Mount wiki](https://iamflipse.github.io/sermon-on-the-mount-wiki/), cross-linked where themes overlap.

## Layout

- `src/` — markdown source pages (`sections/`, `concepts/`, study aids)
- `book/` — mdbook-generated static site (committed for GitHub Pages)
- `tools/mdbook` — mdbook v0.4.21 binary (aarch64 Linux, built from source)

## Rebuild + republish

```sh
./tools/mdbook build -d book
git add -A && git commit -m "update" && git push origin main
# republish: recreate orphan gh-pages branch with book files at root + tools/mdbook, force push
git checkout --orphan gh-pages-new && git rm -rf --cached . >/dev/null
# copy book/* to the root, keep tools/mdbook, commit "Publish: ...", then:
git push -f origin gh-pages-new:gh-pages
```
