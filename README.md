**Out of date** This project is old and needs reviewing. We never completed it, and hopefully some of the tooling we need has already been developed elsewhere. Keeping this for historical reasons, and because I do plan on returning to this work.

# Structure 101g Golang flavor

This is a Golang flavor for the [Structure 101g](https://structure101.com/) static analysis and architectural decision making tool. 

Note: If you're wondering where the code for the runner lives, it's [here](https://github.com/bunniesandbeatings/go-flavor-parser).

## Why?

I used Structure 101 in the past, on Actionscript and Java projects. It was fantastic, really helped me recognize flaws in my dependency tree. Many people miss the value of a well structured, cycle-free dependency tree. For me, it's central to producing code that is easy to reason about.

For many years, I've been primarily a Ruby developer. Unfortunately, Ruby's dynamicism does not lend itself well to static analysis, and I've aborted my attempt to produce a Ruby flavor for Structure 101.  

I'm also developing in Go more and more, not so much by choice but because it fits the needs of products I work with. So despite my misgivings about the expressiveness of Go, I still want to have great tools for working with it. This Structure 101 flavor is one of them.

## Currently

Not much here yet. A simple flavor you have to download, build the binary dependency for, and put in your struct101g folder. It only reads package level dependencies from your app at the moment. 

## Plans

  0. Runner binaries for osx, linux and windows
  0. Tests! Currently this code is a [Spike](http://agiledictionary.com/209/spike/). I'm a TDD guy, but with severe limitations on my time and weak Golang skills, I'm just hacking to prove value. I want to throw my code out and rewrite it with tests driving out the design.
  0. CI, probably on CircleCI.
  0. Node types:
    0. Package (Done!)
      0. Constant
      0. Variable
      0. Function
    0. Type (struct/interface)
      0. Public field
      0. Function
  0. Dependency types:
    0. Import (Done!)
    0. Variable/Const type definition
    0. Field type Definition
    0. Parameter type definition
    0. Return type definition
    0. Function calls
    0. Casts

## Installation
Currently this is only tested on OSX. It should work on any *nix with a bash shell.

0. Install go and make sure your GOPATH is set up
0. Download and build

  ```shell
  git clone https://github.com/bunniesandbeatings/go-flavor
  cd go-flavor
  ./scripts/build
  ```
  
0. Symlink into Struct101g (if you cant find the struct101g folder, run struct101g first and install one of the other flavors)

  ```shell
  ln -s `pwd` $HOME/structure101g/flavors/com.bunniesandbeatings.go-flavor_0.0.1
  ```

0. You must restart Structure 101g, it should have a new Project type under 'New Project' for the Go flavor.

## Usage 

0. In Structure 101g, create a new project
0. Select the "com.bunniesandbeatings.go-flavor" project type
0. click Next
0. For '$GOPATH', enter your gopath. Unfortunately Structure 101g doesn't run the flavor's runner using your shell environment.
0. For 'Package Definition', use a package ref as described by ```go help packages```
  0. For example ```github.com/bunniesandbeatings/go-flavor-parser/...```


# Project backlog

Maintained on the [go-flavor Pivotal Tracker project](https://www.pivotaltracker.com/n/projects/1265846)
