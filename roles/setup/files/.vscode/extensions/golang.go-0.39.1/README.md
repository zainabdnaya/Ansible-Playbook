# Go for Visual Studio Code

[![Slack](https://img.shields.io/badge/slack-gophers-green.svg?style=flat)](https://gophers.slack.com/messages/vscode/)

<!--TODO: We should add a badge for the build status or link to the build dashboard.-->

[The VS Code Go extension](https://marketplace.visualstudio.com/items?itemName=golang.go)
provides rich language support for the
[Go programming language](https://golang.org/).

📣
[Remote attach debugging](https://github.com/golang/vscode-go/wiki/debugging#connecting-to-headless-delve-with-target-specified-at-server-start-up) is now available via Delve's native DAP implementation with Delve v1.7.3 or newer. It enchances remote debugging with the same
[debugging features](https://github.com/golang/vscode-go/wiki/debugging) that are already in use for local debugging. It is now the default with the
[Go Nightly](https://github.com/golang/vscode-go/wiki/nightly) build of the extension and will become the default for the stable releases in mid 2022.
We recommend switching your remote attach configurations in `launch.json` to use
`"debugAdapter":"dlv-dap"` now to verify that this works for you.
Please [file a new issue](https://github.com/golang/vscode-go/issues/new/choose) if you encounter any problems.

📣📣 Watch [Debugging Treasure Hunt](https://youtu.be/ZPIPPRjwg7Q) from [GopherCon 2021](https://www.gophercon.com/) for a fun take on a debugging demo with VS Code Go and Delve DAP.

## Quick Start

Welcome! 👋🏻<br/>
Whether you are new to Go or an experienced Go developer, we hope this
extension fits your needs and enhances your development experience.

1.  Install [Go](https://golang.org) 1.14 or newer if you haven't already.

1.  Install the [VS Code Go extension].

1.  Open any directory or workspace containing Go code to automatically activate
    the extension. The
    [Go status bar](https://github.com/golang/vscode-go/wiki/ui) appears in the
    bottom left corner of the window and displays your Go version.

1.  The extension depends on `go`, `gopls`, `dlv` and other optional tools. If
    any of the dependencies are missing, the ⚠️ `Analysis Tools Missing` warning
    is displayed. Click on the warning to download dependencies.

    See the
    [tools documentation](https://github.com/golang/vscode-go/wiki/tools) for a
    complete list of tools the extension depends on.

<p align="center">
<img src="https://github.com/golang/vscode-go/raw/HEAD/docs/images/installtools.gif" width=75%>
<br/>
<em>(Install Missing Tools)</em>
</p>

You are ready to Go :-) &nbsp;&nbsp; 🎉🎉🎉

## What's next

* Explore more [features][full feature breakdown] of the VS Code Go extension.
* View the
  [settings documentation](https://github.com/golang/vscode-go/wiki/settings)
	and [advanced topics](https://github.com/golang/vscode-go/wiki/advanced) to
	customize the extension.
* View the [tools documentation](https://github.com/golang/vscode-go/wiki/tools)
  for a complete list of tools the VS Code Go extension depends on.
* Solve issues with the
  [general troubleshooting](https://github.com/golang/vscode-go/wiki/troubleshooting)
	and [debugging troubleshooting](https://github.com/golang/vscode-go/wiki/debugging#troubleshooting)
	guides.
* [file an issue](https://github.com/golang/vscode-go/issues/new/choose) for
  problems with the extension.
* Start a [GitHub discussion](https://github.com/golang/vscode-go/discussions)
  or get help on [Stack Overflow].
* Explore Go language resources on [go.dev/learn](https://go.dev/learn) and
  [golang.org/help](https://golang.org/help).

If you are new to Go, [this article](https://golang.org/doc/code.html) provides
the overview on Go code organization and basic `go` commands. Watch ["Getting
started with VS Code Go"] for an explanation of how to build your first Go
application using VS Code Go.

## Feature highlights

* [IntelliSense] - Results appear for symbols as you type.
* [Code navigation] - Jump to or peek at a symbol's declaration.
* [Code editing] - Support for saved snippets, formatting and code organization,
  and automatic organization of imports.
* [Diagnostics] -  Build, vet, and lint errors shown as you type or on save.
* Enhanced support for [testing] and [debugging]

See the [full feature breakdown] for more details.

<p align=center>
<img src="https://github.com/golang/vscode-go/raw/HEAD/docs/images/completion-signature-help.gif" width=75%>
<br/>
<em>(Code completion and Signature Help)</em>
</p>

In addition to integrated editing features, the extension provides several
commands for working with Go files. You can access any of these by opening the
Command Palette (`Ctrl+Shift+P` on Linux/Windows and `Cmd+Shift+P` on Mac), and
then typing in the command name. See the
[full list of commands](https://github.com/golang/vscode-go/wiki/commands#detailed-list) provided by this
extension.

<p align=center>
<img src="https://github.com/golang/vscode-go/raw/HEAD/docs/images/toggletestfile.gif" width=75%>
<br/><em>(Toggle Test File)</em></p>

**⚠️ Note**: the default syntax highlighting for Go files is provided by a
[TextMate rule](https://github.com/jeff-hykin/better-go-syntax) embedded in VS
Code, not by this extension.

For better syntax highlighting, we recommend enabling
[semantic highlighting](https://code.visualstudio.com/api/language-extensions/semantic-highlight-guide)
by turning on [Gopls' `ui.semanticTokens` setting](https://github.com/golang/vscode-go/wiki/settings#uisemantictokens).
    ```
    "gopls": { "ui.semanticTokens": true }
    ```

## Setting up your workspace

The VS Code Go extension supports both `GOPATH` and Go modules modes.

[Go modules](https://golang.org/ref/mod) are used to manage dependencies in
recent versions of Go. Modules replace the `GOPATH`-based approach to specifying
which source files are used in a given build, and they are the default build
mode in go1.16+. We highly recommend Go development in module mode. If you are
working on existing projects, please consider migrating to modules.

Unlike the traditional `GOPATH` mode, module mode does not require the workspace
to be located under `GOPATH` nor to use a specific structure. A module is
defined by a directory tree of Go source files with a `go.mod` file in the
tree's root directory.

Your project may involve one or more modules. If you are working with multiple
modules or uncommon project layouts, you will need to configure your workspace
by using [Workspace Folders]. See the
[Supported workspace layouts documentation] for more information.

## Preview version

If you'd like to get early access to new features and bug fixes, you can use the
nightly build of this extension. Learn how to install it in by reading the
[Go Nightly documentation](https://github.com/golang/vscode-go/wiki/nightly).

## Contributing

We welcome your contributions and thank you for working to improve the Go
development experience in VS Code. If you would like to help work on the VS Code
Go extension, see our
[contribution guide](https://github.com/golang/vscode-go/wiki/contributing) to
learn how to build and run the VS Code Go extension locally and contribute to
the project.

## Code of Conduct

This project follows the
[Go Community Code of Conduct](https://golang.org/conduct). If you encounter a
conduct-related issue, please mail conduct@golang.org.

## License

[MIT](https://github.com/golang/vscode-go/blob/HEAD/LICENSE)

[Stack Overflow]: https://stackoverflow.com/questions/tagged/go+visual-studio-code
[`gopls`]: https://golang.org/s/gopls
[`go`]: https://golang.org/cmd/go
[Managing extensions in VS Code]: https://code.visualstudio.com/docs/editor/extension-gallery
[VS Code Go extension]: https://marketplace.visualstudio.com/items?itemName=golang.go
[Go installation guide]: https://golang.org/doc/install
["Getting started with VS Code Go"]: https://youtu.be/1MXIGYrMk80
[IntelliSense]: https://github.com/golang/vscode-go/wiki/features#intellisense
[Code navigation]: https://github.com/golang/vscode-go/wiki/features#code-navigation
[Code editing]: https://github.com/golang/vscode-go/wiki/features#code-editing
[diagnostics]: https://github.com/golang/vscode-go/wiki/features#diagnostics
[testing]: https://github.com/golang/vscode-go/wiki/features#run-and-test-in-the-editor
[debugging]: https://github.com/golang/vscode-go/wiki/debugging#features
[full feature breakdown]: https://github.com/golang/vscode-go/wiki/features
[workspace documentation]: https://github.com/golang/tools/blob/master/gopls/doc/workspace.md
[`Go: Install/Update Tools` command]: https://github.com/golang/vscode-go/wiki/commands#go-installupdate-tools
[Supported workspace layouts documentation]: https://github.com/golang/tools/blob/master/gopls/doc/workspace.md
[Workspace Folders]: https://code.visualstudio.com/docs/editor/multi-root-workspaces
