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

Every golang program must be part of a package. Where the main package is given the name "package main", and the main package can use other sub packages, in this case, our main package makes use of the 'fmt' package. 
fmt is actually one of the standard library of packages - https://golang.org/pkg/#stdlib - these standard packages comes included with golang itself. 

You can have several files making making up your golang app, in which case all these files will start with 'package main', and the file that contains your 'func main()' is the starting point of your appl. 




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

If you want to build for other targets, e.g. ubuntu, then you need to run with some variable settings:


```
GOOS=linux GOARCH=amd64 go build .
```

This results in:

```bash
$ file ./gsg_hello_world 
./gsg_hello_world: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, not stripped
```


See - https://golang.org/doc/install/source#environment - for more info GOOS, GOARCH and others.


### Why have a function call 'main'

When you run a shell script, it usually is a single file, and the execution happens from the top of the shell script, and works it's way down, hence for the shell script, the top of the file is the starting point. With a golang project. all your code can span across lots of *.go. So you need some way to tell golang where to start the execution from. That's done by defining the main function. 