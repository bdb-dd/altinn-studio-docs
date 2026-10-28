{{- /* For markdown output, emit a fenced code block instead of highlighted HTML */ -}}
{{- $lang := .Get 0 | default "" -}}
```{{ $lang }}
{{ .InnerDeindent | strings.TrimSpace }}
```
