{{- $_hugo_config := `{ "version": 1 }` -}}
{{- $header := .Get "header" | default "expand-default" -}}

<details>
<summary>{{ $header }}</summary>

{{ .InnerDeindent }}

</details>
