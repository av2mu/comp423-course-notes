# Quick Go Setup with Dev Containers

* Primary author: [Anish Toomu](https://github.com/av2mu)

!!! warning "Required Setup"
    - VS Code
    - Docker Desktop running
    - Dev Containers extension in VS Code

## Steps

1. Make project folder:
```bash
mkdir my-go-project
cd my-go-project
git init
```

2. Make dev container config:
```bash
mkdir .devcontainer
```

!!! note "Config File"
    Put this in `.devcontainer/devcontainer.json`:
    ```json
    {
        "name": "Go Dev",
        "image": "mcr.microsoft.com/devcontainers/go:1",
        "customizations": {
            "vscode": {
                "extensions": [
                    "golang.go"
                ]
            }
        }
    }
    ```

3. Hit `F1`, type "reopen in container", click it

4. Set up Go project:
```bash
go version   
go mod init my-go-project
```

5. Make `main.go`:
```go
package main

import "fmt"

func main() {
    fmt.Println("Hello COMP423")
}
```

!!! tip "Running Options"
    ```bash
    go run main.go     # run directly
    go build main.go   # make exe file (like gcc in COMP211)
    ./main            # run exe (use .\main.exe on Windows)
    ```

!!! info "Build vs Run"
    - `go build` works like `gcc` from COMP211 - it creates an executable file
    - `go run` is different - it compiles and runs in one step without making an exe file