# Project Content Model

The `kinaz_project` post type uses WordPress core fields plus structured metadata.

## Core fields

| Field | Usage |
| --- | --- |
| Title | Public project name and default SEO title |
| Editor | Optional long-form editorial content |
| Excerpt | Card/fallback summary |
| Featured image | Archive card and project hero |
| Menu order | Manual ordering signal |

## Structured metadata

All keys below are stored with the `_kinaz_` prefix.

### Identity

- `subtitle`, `location`, `district`, `type`, `status`, `year`, `scope`
- `developer`, `consultant`, `coordinates`, `start_date`, `completion_date`

### Metrics

- `area`, `value`, `units`, `duration`, `completion`

### Narrative

- `intro`, `challenge`, `solution`, `result`, `disclosure`
- `scope_details`: one stage per line using `Stage | Description | Status`
- `features`: one feature per line
- `investment`: one point per line using `Title | Description`

### Media and links

- `gallery`: comma-separated attachment IDs
- `brochure_id`: PDF attachment ID
- `video_url`: oEmbed-compatible video URL
- `map_url`: public map URL
- `featured`: whether the project appears in the homepage portfolio

### SEO

- `seo_title`: optional project document title override
- `seo_description`: optional meta description

## Extension guidance

- Add or sanitize new project metadata in `inc/post-types.php`.
- Render public project fields in `single-kinaz_project.php`.
- Keep optional sections conditional so incomplete projects remain visually clean.
- Use attachment IDs rather than hardcoded upload URLs when adding media controls.

