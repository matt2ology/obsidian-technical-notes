---
aliases:
note-type: permanent
date-created: 2024-02-15
long-form-date-created: Thursday, February 15, 2024
week-created: Week 07.4
time-created: 11:03 PM
---

# Readwise Obsidian Export Formatting

Related : [Kindle Highlight Sync Note Format](Kindle%20Highlight%20Sync%20Note%20Format.md)

## Page metadata

```django
{% if image_url -%}

![rw-book-cover]({{image_url}})

{% endif -%}
## Metadata
- Author: {% if author %}[[{{author}}]]{% endif %}
- Full Title: {{full_title}}
- Category: #{{category}}
{% if document_note -%}
- Document Note: {{document_note}}
{% endif -%}
{% if document_tags -%}
- Document Tags: {% for tag in document_tags %}[[{{tag}}]] {% endfor %}
{% endif -%}
{% if url -%}
- URL: <{{url}}>
{% endif -%}
{% if summary -%}
## Summary

{{summary}}
{% endif -%}
```

## Highlights header

```django
{% if is_new_page %}
## Highlights
{% elif has_new_highlights -%}
## New highlights added {{date|date('F j, Y')}} at {{time}}
{% endif -%}
```

## Highlight

```django
{% if highlight_note %}{{ highlight_note }}{% endif %}

> {{ highlight_text }}{% if highlight_location and highlight_location_url %} ([{{highlight_location}}]({{highlight_location_url}})){% elif highlight_location %} ({{highlight_location}}){% endif %}{% if highlight_tags %}
- Tags: {% for tag in highlight_tags %}[[{{tag}}]] {% endfor %}{% endif %}

---
```

## YAML front matter

```yaml
author: { { author } }
category-tag: { { category } }
source-tag: { { source } }
```
