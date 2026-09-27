# Kinaz Real Estate Theme

Custom Arabic-first WordPress theme for Kinaz Real Estate. The theme is built as a structured content system: editors manage projects, articles, inquiries, homepage media, and contact data from WordPress without editing templates.

## Administration

- **Kinaz Dashboard:** `wp-admin/admin.php?page=kinaz-dashboard`
- **Projects:** structured project editor with identity, metrics, story, media, map, brochure, video, and SEO tabs.
- **Site Settings:** `wp-admin/admin.php?page=kinaz-site-settings`
- **Blog:** standard WordPress posts.
- **Inquiries:** private `kinaz_inquiry` records with an internal follow-up status.

## Theme Structure

```text
assets/
  css/                  Frontend and administration styles
  images/               Packaged fallback assets
  js/                   Frontend experiences and administration UI
inc/
  admin.php             Kinaz dashboard and central site settings
  blog.php              Blog content and seed helpers
  customizer.php        Legacy Customizer compatibility
  inquiries.php         Secure inquiry workflow
  post-types.php        Project content model and project editor
template-parts/         Reusable frontend components
front-page.php          Scroll-led homepage
single-kinaz_project.php Project detail template
archive-kinaz_project.php Project archive
```

## Content Rules

1. The featured image is the project cover.
2. The structured project fields drive the cinematic project detail template.
3. Empty fields are omitted safely from the public page.
4. Media selected in **Site Settings** overrides packaged assets; clearing a selection restores the theme fallback.
5. The homepage hero accepts an ordered sequence of Media Library images. When no custom sequence exists, the packaged 20-frame sequence is used.

## Development Notes

- Theme version: `KINAZ_VERSION` in `functions.php`.
- Text domain: `kinaz`.
- Frontend direction is forced to RTL/Arabic while the WordPress admin may use any locale.
- Project metadata is stored with the `_kinaz_` prefix.
- All public output is escaped at render time; admin writes use nonces, capability checks, and field-specific sanitization.
- No page-builder dependency is required.

See [`docs/PROJECT-CONTENT-MODEL.md`](docs/PROJECT-CONTENT-MODEL.md) for the field reference.

