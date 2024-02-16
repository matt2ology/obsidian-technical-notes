---
aliases: 
note-type: permanent
date-created: 2024-02-15
long-form-date-created: Thursday, February 15, 2024
week-created: Week 07.4
time-created: 11:06 PM
---

# Kindle Highlight Sync Note Format

Related : [Readwise Obsidian Export Formatting](Readwise%20Obsidian%20Export%20Formatting.md)

## File Content

```django

# {{longTitle}}

## Metadata

{% trim %}
{% if authorUrl %}
* Author: [{{author}}]({{authorUrl}})
{% elif author %}
* Author: [[{{author}}]]
{% endif %}
{% if asin %}* ASIN: {{asin}}{% endif %}
{% if isbn %}* ISBN: {{isbn}}{% endif %}
{% if pages %}* Pages: {{pages}}{% endif %}
{% if publication %}* Publication: {{publication}}{% endif %}
{% if publisher %}* Publisher: {{publisher}}{% endif %}
{% if url %}* Reference: {{url}}{% endif %}
{% if appLink %}* [Kindle link]({{appLink}}){% endif %}
{% endtrim %}

## Highlights

{{highlights}}
```

## Highlight

```django

{% if note %}{{note}}{% endif %}

> {{ text }} — location: [{{ location }}]({{ appLink }})

---
```
