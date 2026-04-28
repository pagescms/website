---
title: Operations
description: Control create, rename, and delete behavior for content entries.
---

Use `operations` to allow or block create, rename, and delete in the UI for a specific `content` entry.

## Keys

Key | Description
--- | ---
<code class="text-[var(--prism-keyword)]">create</code> | Allow creating new entries/files for this content entry.
<code class="text-[var(--prism-keyword)]">rename</code> | Allow renaming entries/files for this content entry.
<code class="text-[var(--prism-keyword)]">delete</code> | Allow deleting entries/files for this content entry.

## Defaults

Defaults depend on `type`:

Type | create | rename | delete
--- | --- | --- | ---
`collection` | `true` | `true` | `true`
`file` | `true` | `false` | `true`

## Notes

- `settings` (`.pages.yml`) are separate from `content`; deleting settings is disabled by default.
- Any key can be set to `false` to block that operation for the entry.

## Examples

### Disable delete for a single file

```yaml
content:
  - name: site
    label: Site settings
    type: file
    path: data/site.yml
    operations:
      delete: false
```

### Disable rename and delete for a collection

```yaml
content:
  - name: posts
    type: collection
    path: content/posts
    operations:
      rename: false
      delete: false
```
