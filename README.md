# G01f Execute Url

Execute code from the url in order to make games encoded entirely in an url or qr code.

Currently only javascript and html are supported.

## Examples

https://g01f.eu?w=400&d=Hello_Canvas#c.fillText('HelloWorld',10,10)

https://g01f.eu?s=b&e=&d=Hello_HTML#PGgxPkhlbGxvIFdvcmxkPC9oMT4K

https://g01f.eu?s=o&e=&d=Minisweeper_by_Troido#PGJvZHkgb25sb2FkPSdtPTI1Njtmb3IoaT0yNzI7aS0tO2MuaW5uZXJIVE1MKz1pJTE3P2A8YSBvbmNsaWNrPXRoaXMub3V0ZXJIVE1MPWNbaj0ke20tPWNbaV09TWF0aC5yYW5kb20oYT1hbGVydCk8LjIsaX1dP2EoIkJPT00iKXx8IlgiOjgtZigxLC0tbXx8YSgiPUQiKSktZigxNiktZigxNyktZigxOCk+IzwvYT4gYDpgXG5gKWY9eD0+IWNbait4XSshY1tqLXhdJz48cHJlIGlkPWM+Cg==

https://g01f.eu?d=Magic_Powder_by_Troido_and_Qqwy&w=800&h=450&e=#Zm9yKF89JzAwfmZma34waiJiYTg3YTc3NzdkZjA3MzNmMzBrNzQ0NDA3ZmR+YWFhajdrNzN+OTA5NzUwN345MGYwZjBrazBhMGthNzEwNSJXK1dbQV1WbmV3IFQ9VFVpbnRTQXJyYXlSUzMyUihRMHhQLFBPTzM5Tl18PUw9NDstNDxLYiZKSlBIcltHdVtGODMkKGI+PiMmJiEhMTI4PDwjHy5maWxsKFAeY34xah0zNkU0HDgwG2JPGhswGSsZKhhjMU8XZT1kFj10Lm9rc2V0FSk7FDE2EyYxNSkrOF1eQhJJbWFnZURhdGEoESEoEC0tOykPPXQ9Pg4pLAxvbm1vdXNlCyYxOTIpPChKMTkyKXx8CWZvcigIR2VdB01hdGgucmFuZG9tKCkGFitbMSwtMSwZLC0ZXVs0KgZ8MF0FFisoKAYtLjUpKigxKyhKNikpfDApBBBiPUYjMTkSDAMsbT1IN2owHxMmNwwCByZtAwcmbBAHPUYjMjYSKQFmPWc9aD1CPXA9MDtyURwUch4dFHU9W1AzZThiYxozNCRjGjEwF2M5OWMwOGZPNDckNGZPNRM4NDhkTjE4YzA2ZE5mMyQ5GjdmYjE4Zk81MWU4NDc3LDQ3M08dTzEzMDM4MRczN2NkJBcTORsxZjNPOWRiLDU5OU80MDM2JBcxM2QZYjNPNmphGjVqYRozNGQzODFjGjY4OBtlZk5mMxs1N107dj17fTsIQSBpblcpdltGQS8zfDBdTCgiUCJWVnwwKTw8QSUzKjg7bj1UUkJ1a2VyKDE0NEU0FENRbhR3UzhDbGFtcGVkUihuFGEuC2Rvd24OZj0xOwt1cA5mPTA7YS4LbW92ZQ57ZxVYO2gVWX07b253aGVlbA5wKz0wPHQuZGVsdGFZfHwxMTtzZXRJbnRlcnZhbCh0PT57Qx5ramoUCHlLeQ8IeEt4DwhmEEdnGGgreBh5XT1GcCUxMl1eQgxBPTEyO0EPQ1sTKxMqQSt4GHkrUGMbKihBPT1wJTEyKStQYxtMdltGQV1dO0JePTE7CGQ9HDtkD2I9R2RdLGJeUB0QMSZiKT09QhBsPUgzGWofMjMmNykCQ1tkTHZbYnwxXSxKMzIhLjE+BgNIGTAQSDRqajA/Fi0ZOigFLAECBQwBDAQYKChKOCExKS0oShMhLjU8BikMHD5lITA8ZRAHCUo0EEcEXQkoFgxIGTB8fCgBDEdkXT0HLAc9Yl4xFGMucHV0EVQRdywZLDQ1MAwwLDApfSwTKSc7Rz0vW14gIiUtRUlNVVgtaWwtfV0vLmV4ZWMoXyk7KXdpdGgoXy5zcGxpdChHKSlfPWpvaW4oc2hpZnQoKSk7ZXZhbChfKQ==

## Structure

The code can be either in the `c` query parameter or in the fragment part of the url

The following query parameters are relevant:

- *e*: The encoding used for the sourcecode. Setting this to the empty or to `b64` will interpret the source code as base46 encoded. Omitting this will take the characters from the url without any decoding
- *s*: The context for executing the code:
  - `empty`: run the code without any additional context
  - `c`: Create a canvas and run the code as JS
  - `b`: Replace the html inside the document body with the code
- *d*: The description. This will be shown in the bottom of the page. Underscores in the description will be replaced with spaces.
- *w*: The width of the canvas. Implies `s=c`. Default is window.innerWidth
- *h*: The height of the canvas. Implies `s=c`. Default is window.innerHeight

The following shorthands are available in the javascript code (set on the global `window` object):

- `b`: `document.body`
- `a`: The canvas (if it exists);
- `c`: The RenderingContext2D of the canvas (if it exists);




