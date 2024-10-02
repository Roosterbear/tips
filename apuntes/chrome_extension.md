# CHROME Extensions

## manifest.json

```json
{
  "manifest_version":2,
  "name":"Hello World",
  "version":"1.0",
  "description":"A Hello World Extension",
  "icons":{
    "128":"icon128.png",
    "48":"icon48.png",
    "16":"icon16.png",
  },
  "browser_action":{
    "default_icon":"icon16.png",
    "default_popup":"popup.html",
  },
  "permissions":[
    "storage"
  ]
}
```

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello World</title>
  </head>
  <body>
    <h2 id="greet">Hello World<h2>
  </body>
</html>
```