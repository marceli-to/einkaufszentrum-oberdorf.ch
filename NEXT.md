# Progress / Next

## Done

- **2026-11-13** — Security update Craft CMS 4.17.15 → 4.18.9 (`499e757`).
  Fixes critical CVE-2026-55791 (Host header SSRF/JS injection), high
  CVE-2026-72778 / CVE-2026-72781 (authenticated RCE), yii2 2.0.55
  (CVE-2026-39850). Tested locally: no pending migrations, homepage 200.

## Next

- [ ] Deploy to production: `composer install` + `php craft migrate/all --interactive=0`
      (add `--no-security-blocking` if Composer blocks on `enshrined/svg-sanitize`).
- [ ] Set new CP password for m@marceli.to on production:
      `php craft users/set-password m@marceli.to`
- [ ] Plan Craft 5 upgrade — Craft 4.18.9 pins `twig/twig` ~3.19.0 (incl. critical
      CVE-2026-46633) and `enshrined/svg-sanitize` ~0.22.0, both with open advisories
      that can't be fixed on Craft 4.
- [ ] Replace abandoned `craftcms/redactor` with `craftcms/ckeditor` (part of Craft 5 move).

## Notes

- Control panel: `/adm` (`CP_TRIGGER` in `.env`; falls back to `/admin` if unset).
