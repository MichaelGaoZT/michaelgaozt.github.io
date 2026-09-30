# Ziteng Gao · 高紫腾

Personal academic homepage, with a layout inspired by [Zhengyi Luo’s website](https://www.zhengyiluo.com/) and [al-folio](https://github.com/alshedivat/al-folio). This is a small, independently implemented static site, not an installation of the full Jekyll theme. Pages work without JavaScript; a small script enhances the mobile navigation.

## Preview locally

No npm, Ruby, or third-party Python packages are required. Use Python 3.9 or newer:

```sh
python3 scripts/build.py
python3 scripts/check_site.py
python3 -m http.server 8000 --bind 127.0.0.1
```

Open http://localhost:8000. When connecting to this server through VS Code, forward port 8000 first.

## Edit the site

- `src/pages/index.html`: English biography, news, selected research, affiliations, and experience.
- `src/pages/cn.html`: Chinese biography and contact information.
- `src/pages/hobbies.html`: badminton page.
- `src/layout.html`: shared page shell, metadata, navigation, and footer.
- `assets/css/main.css`: responsive styles.
- `assets/images/`: photographs, research image, and institution logos from the old site.
- `assets/files/ZitengGao_CV.pdf`: the original CV download.

After editing the source fragments or layout, run `python3 scripts/build.py` and commit the generated `index.html`, `cn/index.html`, and `hobbies/index.html` together with the source changes. Validate with:

```sh
python3 scripts/build.py --check
python3 scripts/check_site.py
```

## Publish with GitHub Pages

The repository is ready for GitHub Pages branch publishing; `.nojekyll` serves the generated HTML directly.

1. Open [Settings → Pages](https://github.com/MichaelGaoZT/michaelgaozt.github.io/settings/pages).
2. Select **Deploy from a branch**, then **main** and **/ (root)**, and save.
3. Wait for the GitHub Pages deployment to finish.

The website URL is **https://michaelgaozt.github.io/**. This is the account-level GitHub Pages repository for `MichaelGaoZT`. Internal links use relative paths, and canonical URLs and social preview images use this root URL. If the hosting URL changes, update `SITE_URL` in `scripts/build.py` and rebuild.

No custom domain is configured. The previous `CNAME`, which named the default GitHub Pages domain, is no longer needed.

## Previous homepage backup

Before replacing the old site on September 30, 2026, its exact `main` commit, `05b321321cc02d54767d4e061979a5084d19c64d`, was saved and pushed to [backup/old-homepage-20260930](https://github.com/MichaelGaoZT/michaelgaozt.github.io/tree/backup/old-homepage-20260930). This branch preserves the previous site, assets, and configuration.

The redesigned site was synchronized from [MichaelGaoZT/ZitengGao2000.github.io](https://github.com/MichaelGaoZT/ZitengGao2000.github.io) at commit `edc67e584cf82f6ab2d239aec5e7db3eaad8d467`. Only hosting metadata, the footer source link, and repository documentation were adapted for this root site. The source repository remains independent; this synchronization does not set up automatic mirroring.

## Migration notes

Content was migrated from `MichaelGaoZT/michaelgaozt.github.io` at commit `05b3213`, using the authentic English homepage, Chinese page, and hobbies page. News and experience dates are preserved from that source, whose biography was last updated in March 2026. The inherited hidden pages containing another person's publications, services, awards, social accounts, and meeting links were excluded. No publication venue or acceptance status has been inferred for TouchAnything.

The original CV PDF is preserved as supplied. It predates the Ph.D. update, still lists XPENG as “Present,” and has some dates that differ from the current homepage. Replace it with an updated CV when available; the new website uses the current homepage dates.

## License and credits

Original website code is distributed under the [MIT License](LICENSE). Personal text, CV, photographs, research figures, and third-party logos are outside the code license; their rights remain with their respective owners. This scope statement does not revoke any rights already granted for material in the old repository.

The visual reference is Zhengyi Luo’s al-folio-based homepage. The implementation here uses original HTML/CSS/JavaScript and does not redistribute his biography, research, photos, or site source. Original personal material comes from Ziteng Gao’s previous homepage.
