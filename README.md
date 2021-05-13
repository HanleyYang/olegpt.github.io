# plantuml-code-highlight

Javascript necessary to render plantuml from content in a html-block of class "language-plantuml".  Possible to use with Gitea.

## Install
Copy the javascript files to your server. Then to convert all html blocks having the class `language-plantuml` add the following to the html page:
```html
<script src="https://your-server.com/deflate.js"></script>
<script src="https://your-server.com/encode.js"></script>
<script src="https://your-server.com/plantuml_codeblock_parse.js"></script>
<script>
parsePlantumlCodeBlocks("http://www.plantuml.com/plantuml,"language-plantuml")
</script>
```

Specifically for Gitea: Copy the javascript files to your `custom/public` folder. Then place the following code in `custom/templates/custom/footer.tmpl`:
```html
{{if .RequireHighlightJS}}
<script src="https://your-server.com/deflate.js"></script>
<script src="https://your-server.com/encode.js"></script>
<script src="https://your-server.com/plantuml_codeblock_parse.js"></script>
<script>
parsePlantumlCodeBlocks("http://www.your-plantuml-server.com/plantuml")
</script>
{{end}}
```

## License
- deflate.js: Copyright (C) 1999 Masanao Izumo <iz@onicos.co.jp>. Some sources claim this to be GPL-2
- encode.js: From https://plantuml.com/code-javascript-synchronous. GPL-3
- plantuml_codeblock_parse.js: David Svantesson. MIT or GPL-2 or GPL-3 at your choice.

