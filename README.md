# EQRcode

Simple QR Code Generator written in Elixir with no other dependencies.

To generate the SVG QR code:

```elixir
qr_code_content = "your_qr_code_content"

qr_code_content
|> EQRCode.encode()
|> EQRCode.svg()
```

<img src="./screenshots/default.png?raw=true" width="300">

### Options

You can also pass in options into `EQRCode.svg()`:

```elixir
qr_code_content
|> EQRCode.encode()
|> EQRCode.svg(color: "#03B6AD", shape: "circle", width: 300)
```

<img src="./screenshots/circle-color.png?raw=true" width="300">

You can specify the following attributes of the QR code:

* `color`: In hexadecimal format. The default is `#000`
* `shape`: Only `square` or `circle`. The default is `square`
* `width`: The width of the QR code in pixel. Without the width attribute, the QR code size will be dynamically generated based on the input string.
* `viewbox`: When set to `true`, the SVG element will specify its height and width using `viewBox`, instead of explicit `height` and `width` tags.

Default options are `[color: "#000", shape: "square"]`.

## Installation

```elixir
def deps do
  [
    {:eqrcode, "~> 0.1.4"}
  ]
end
```

## Credits

We reused most of the code from [sunboshan/qrcode](https://github.com/sunboshan/qrcode) to generate the matrix required to render the QR Code. We also reference [rqrcode](https://github.com/whomwah/rqrcode) on how to generate SVG from the QR Code matrix.

## License

This project is Licensed under the [MIT License](https://github.com/SiliconJungles/eqrcode/blob/master/LICENSE).
