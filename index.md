---
layout: default
---

| Tool | Linux | Windows | In this state since…  |
|-----:|:-----:|:-------:|:----------------------|
{%- for status in site.data.latest %}
| {{ status.tool }}
{{- "|" -}}
<span class="status-{{ status.linux }}">{{ status.linux | replace: '-', ' ' }}</span>
{{- "|" -}}
<span class="status-{{ status.windows }}">{{ status.windows | replace: '-', ' ' }}</span>
{{- "|" -}}
<a href="https://github.com/rust-lang/rust/commit/{{ status.commit }}">{{ status.commit | truncate: 9, "" }}</a> on <date datetime="{{ status.datetime }}">{{ status.datetime | date: "%Y-%m-%d %H:%M:%S" }}</date> |
{%- endfor %}

The table above reflects the real-time status on the master branch. 
Please also check <https://rust-lang.github.io/rustup-components-history/> for availability of each component on nightly.
