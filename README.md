# WordPress maintenance report

English · [Português](README.pt-BR.md)

## Status

Archived (2026-11). One-off deliverable from May 2025. There is no code here, only the record of the service.

## What it does

A maintenance job (May 3, 2025) on the WordPress site of a small company. The work had three parts:

- **PHP update.** PHP upgraded to the latest version compatible with the theme and plugins; `memory_limit`, `max_execution_time` and upload limits raised in `php.ini` and `.htaccess`; compatibility tested afterwards.
- **Performance.** CSS and JS minified, browser cache and gzip compression turned on in `.htaccess`, unused plugins and scripts removed, images compressed.
- **Security.** Security headers (`X-Frame-Options`, `X-Content-Type-Options`, a `Content-Security-Policy`), tighter file permissions on `wp-config.php`, malware scan, all plugins and themes updated, PHP execution blocked in `uploads/`, HTTPS and the main domain enforced by redirect.

A full backup (files and database) was taken before any change and a final backup was handed to the client.

## What was learned

- **Back up before touching anything.** It is what makes the rest of the job safe to do on a live site.
- **Raising limits is not a fix.** Bigger `memory_limit` and `max_execution_time` hide slow plugins. Removing what was not used did more for speed than the new limits.
- **Headers age.** `X-XSS-Protection` was in the original report; modern browsers ignore it and the current advice is a good `Content-Security-Policy` instead.
- **A report is part of the delivery.** Writing down every change made the job easy to explain to the client and easy to undo.

## License

All rights reserved. Published as portfolio; not licensed for reuse. See [LICENSE](LICENSE).
