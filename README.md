```bash
$ go get github.com/Sher-Chowdhury/gsg_hello_world
$ go run github.com/Sher-Chowdhury/gsg_hello_world
hello world
```

also: 

```bash
$ export PATH=$PATH:~/go/bin/
$ gsg_hello_world
hello world
```

To learn more about the fmt package do:

```bash
$ go doc fmt
...
$ go doc fmt.Println
...
```

## build from source

```bash
git clone git@github.com:Sher-Chowdhury/gsg_hello_world.git
cd gsg_hello_world
```

Note, this repo has a go.mod. this file was created by running:

```bash
go mod init github.com/Sher-Chowdhury/gsg_hello_world.git
```

Then check your code is working:

```go
go run .
hello world
```

Then build your binary, and run it:

```go
go build .
```

This creates the following file executable:

```go
$ ./gsg_hello_world
hello world
```

I'm using a macbook, so this executable will only work on macbooks.

```bash
$ file ./gsg_hello_world 
./gsg_hello_world: Mach-O 64-bit executable x86_64
```

If you want to build for other targets, e.g. ubuntu, then you need to run:


```
GOOS=linux GOARCH=amd64 go build .
```

This results in:

```bash
$ file ./gsg_hello_world 
./gsg_hello_world: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, not stripped
```


See - https://golang.org/doc/install/source#environment