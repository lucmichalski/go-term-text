# go-term-text

[![Build Status](https://travis-ci.org/MichaelMure/go-term-text.svg?branch=master)](https://travis-ci.org/MichaelMure/go-term-text)
[![GoDoc](https://godoc.org/github.com/MichaelMure/go-term-text?status.svg)](https://godoc.org/github.com/MichaelMure/go-term-text)
[![Go Report Card](https://goreportcard.com/badge/github.com/MichaelMure/go-term-text)](https://goreportcard.com/report/github.com/MichaelMure/go-term-text)
[![codecov](https://codecov.io/gh/MichaelMure/go-term-text/branch/master/graph/badge.svg)](https://codecov.io/gh/MichaelMure/go-term-text)
[![GitHub license](https://img.shields.io/github/license/MichaelMure/go-term-text.svg)](https://github.com/MichaelMure/go-term-text/blob/master/LICENSE)
[![Gitter chat](https://badges.gitter.im/gitterHQ/gitter.png)](https://gitter.im/the-git-bug/Lobby)

`go-term-text` is a go package implementing a collection of algorithms to help format and manipulate text for the terminal.

In particular, `go-term-text`:
- support wide characters (chinese, japanese ...)
- handle properly ANSI escape sequences

## Example

```go
package main

import (
	"fmt"
	"strings"

	text "github.com/MichaelMure/go-term-text"
)

func main() {
	input := "The \x1b[1mLorem ipsum\x1b[0m text is typically composed " +
		"of pseudo-Latin words. It is commonly used as placeholder text" +
		" to examine or demonstrate the visual effects of various graphic" +
		" design. 一只 A Quick 敏捷\x1b[31m的狐 Fox 狸\x1b[0m跳过了Dog一只懒狗。"

	output, n := text.WrapWithPadIndent(input, 60, "        ", "    ")

	fmt.Printf("output has %d lines\n\n", n)

	fmt.Println("|" + strings.Repeat("-", 58) + "|")
	fmt.Println(output)
	fmt.Println("|" + strings.Repeat("-", 58) + "|")
}

```

This will print:

![example output](/img/example.png)

For more details, have a look at the [GoDoc](https://godoc.org/github.com/MichaelMure/go-term-text).

## Origin

This package has been extracted from the [git-bug](https://github.com/MichaelMure/git-bug) project. As such, its aim is to support this project and not to provide an all-in-one solution. Contributions as welcome though.

## Contribute

PRs accepted.

## License

MIT