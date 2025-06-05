<p align="center">
  <img src="https://github.com/user-attachments/assets/637a0ffc-b1a2-48e5-b468-29f41fb30a08" 
       alt="Muvius Framework Logo" 
       width="180" 
       style="padding: 10px; border-radius: 8px;"/>
</p>

# Goofy

**Goofy** is a modular and extensible Go package designed to help developers build robust RESTful services rapidly. It provides a clean interface for defining agent-like behaviors with built-in support for metrics, tracing, PostgreSQL connectivity, and CLI-driven workflows.

## Features

- ✅ **Inbuilt Metrics**: Prometheus-compatible metrics collection.
- 🧵 **Tracing Support**: Distributed tracing support with OpenTelemetry.
- 🌐 **Full REST Support**: Supports all standard HTTP methods (GET, POST, PUT, DELETE, PATCH).
- ⚡ **Rapid API Bootstrapping**: Start a runnable REST API server in minutes.
- 🛠️ **Command-Line Migrations**: Built-in CLI for managing PostgreSQL database migrations.
- 🛢️ **Auto PostgreSQL Connect**: Automatically connects to a configured PostgreSQL instance on startup.
- 🧩 **Pluggable Architecture**: Easily define custom logic via the `Goofy` interface.

## Installation

```bash
go get github.com/varun-singhh/goofy/pkg/goofy
```
Then, import it in your Go code:
```bash
import "github.com/varun-singhh/goofy/pkg/goofy"
```
Usage

Here’s a minimal example of how to use the Goofy package:
```bash
package main

import (
    "fmt"
    "github.com/varun-singhh/goofy/pkg/goofy"
)

type MyGoofy struct{}

func (g *MyGoofy) Do() error {
    fmt.Println("Hello from MyGoofy!")
    return nil
}

func main() {
    g := goofy.New(
        goofy.WithGoofy(&MyGoofy{}),
    )

    if err := g.Run(); err != nil {
        fmt.Println("Error:", err)
    }
}
```
API Overview

Goofy Interface
```bash
type Goofy interface {
    Do() error
}
```
Options Struct

Used to configure and build a Goofy instance.
```bash
type Options struct {
    goofy Goofy
}
```
New(opts ...Option) *GoofyEngine

Creates a new Goofy engine with the given options.
```
Run() error
```
Executes the Goofy’s Do() method.

Contributions are welcome! To contribute:
- Fork the repository.
- Create your feature branch (git checkout -b feature/fooBar).
- Commit your changes (git commit -am 'Add fooBar').
- Push to the branch (git push origin feature/fooBar).
- Create a new Pull Request.

License

This project is licensed under the MIT License. See the LICENSE for details.
