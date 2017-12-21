---
layout: default
---

| Tool | Linux | Windows | First affected commit |
|-----:|:-----:|:-------:|:----------------------|
{%- for status in site.data.latest %}
| {{ status.tool }}
{{- "|" -}}
<span class="status-{{ status.linux }}">{{ status.linux | replace: '-', ' ' }}</span>
{{- "|" -}}
<span class="status-{{ status.windows }}">{{ status.windows | replace: '-', ' ' }}</span>
{{- "|" -}}
<a href="https://github.com/rust-lang/rust/commits/{{ status.commit }}">{{ status.commit | truncate: 9, "" }}</a> on <date datetime="{{ status.datetime }}">{{ status.datetime | date_to_string }}</date> |
{%- endfor -%}
