# Abu Dhabi Scouts

The website for [1st Abu Dhabi Scouts](https://1stadscouts.org), built with
[Hugo](https://gohugo.io) and the
[`british-scout-group`](https://github.com/petemahon/hugo-british-scout-group)
theme.

---

## Local development

You need the **extended** edition of Hugo, version 0.128 or newer.

```sh
# macOS
brew install hugo

# Windows
winget install Hugo.Hugo.Extended

# Ubuntu / Debian
# Download the latest hugo_extended_*_linux-amd64.deb from
# https://github.com/gohugoio/hugo/releases and:
sudo dpkg -i hugo_extended_*_linux-amd64.deb
```

Clone with submodules so the theme comes along:

```sh
git clone --recurse-submodules https://github.com/petemahon/adscouts.git
cd adscouts
hugo server
# open http://localhost:1313
```

If you cloned without `--recurse-submodules`:

```sh
git submodule update --init --recursive
```

---

## Editing the home page

Everything visible on the site is in `content/_index.md`. The page front
matter lists `[[sections]]` in order, and each one is rendered by a partial
in the theme. To change copy, button URLs, or section order, edit that file.

For the section type reference, see the
[theme README](https://github.com/petemahon/hugo-british-scout-group#section-types).

---

## Updating the theme

```sh
git submodule update --remote themes/british-scout-group
git add themes/british-scout-group
git commit -m "Update theme to latest"
git push
```

---

## Deployment

A GitHub Actions workflow at `.github/workflows/hugo.yml` builds and deploys
the site to GitHub Pages on every push to `main`. To configure once:

1. **Repository → Settings → Pages → Build and deployment → Source**:
   "GitHub Actions".
2. Add `1stadscouts.org` to the `static/CNAME` file (already done).
3. Configure DNS at the domain registrar to point to GitHub Pages.

---

## Licence

Site content © Abu Dhabi Scouts. The theme is licensed separately —
see the theme repository.
