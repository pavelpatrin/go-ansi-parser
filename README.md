
<p align="center" style="text-align: center">
   <img src="logo.png"><br/>
</p>
<p align="center">
   A library for parsing ANSI encoded strings<br/><br/>
   <a href="https://github.com/leaanthony/go-ansi-parser/blob/master/LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg"></a>
   <a href="https://goreportcard.com/report/github.com/leaanthony/go-ansi-parser"><img src="https://goreportcard.com/badge/github.com/leaanthony/go-ansi-parser"/></a>
   <a href="http://godoc.org/github.com/leaanthony/go-ansi-parser"><img src="https://img.shields.io/badge/godoc-reference-blue.svg"/></a>
   <a href="https://github.com/leaanthony/go-ansi-parser/issues"><img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat" alt="CodeFactor" /></a>
   <a href="https://app.fossa.io/projects/git%2Bgithub.com%2Fleaanthony%2Fgo-ansi-parser?ref=badge_shield" alt="FOSSA Status"><img src="https://app.fossa.io/api/projects/git%2Bgithub.com%2Fleaanthony%2Fgo-ansi-parser.svg?type=shield"/></a>
</p>

Go ANSI Parser converts strings with [ANSI escape codes](https://en.wikipedia.org/wiki/ANSI_escape_code)
into a slice of structs that represent styled text. Features:

  * Can parse ANSI 16, 256 and TrueColor
  * Supports all styles: Regular, Bold, Faint, Italic, Blinking, Inversed, Invisible, Underlined, Strikethrough
  * Provides RBG, Hex, HSL, ANSI ID and Name for parsed colours
  * Configurable colour map for customisation
  * 100% Test Coverage

# Installation
```shell
go get github.com/leaanthony/go-ansi-parser
```

## Usage

```go
var text, err = ansi.Parse("\u001b[1;31;4mHello World\033[0m")

// is the equivalent of...

var text = []*ansi.StyledText{
    {
        Label: "Hello World",
        FgCol: &ansi.Col{
            Id:   9,
            Hex:  "#ff0000",
            Rgb:  &ansi.Rgb{ R: 255, G: 0, B: 0 },
            Hsl:  &ansi.Hsl{ H: 0, S: 100, L: 50 },
            Name: "Red",
        },
        BgCol: null,
        Style: 1,
    },
}
```

