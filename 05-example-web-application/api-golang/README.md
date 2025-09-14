```bash
mkdir go-workspace
# For Linux/macOS
export GOPATH=$PWD/go-workspace
# For Windows
$env:GOPATH=(Join-Path (Get-Location) 'go-workspace'); New-Item -ItemType Directory -Force -Path $env:GOPATH | Out-Null

go mod download
go run main.go
```