# Day 1 - Getting Started

We're going to try and follow the guide here: http://learnyouahaskell.com/

During this month of haskell, we're going to use `stack`. Haskell's blessed package manager is cabal, but stack appears to be the yarn of the haskell world. Stack will help manage dependencies, bootstrap new projects, and run your code. You can download it with one of the following commands:

> curl -sSL https://get.haskellstack.org/ | sh

or

> wget -qO- https://get.haskellstack.org/ | sh

## Let's get started!

```bash
stack new my-project
cd my-project
stack setup
stack build
stack exec my-project-exe
```

## Commands

Here are some interesting commands you can run:

- `stack`: get a list of all the things stack can do for you
- `stack templates`: get a list of all the templates stack can use to bootstrap a new project
- `stack new my-project`: create a new project called my-project using the default template
- `stack setup`: install ghc (haskell compiler) if needed
- `stack build`: install all the dependencies necessary for the project, and build a binary
- `stack ghci`: run an interactive repl with your `/src` folder as the context
- `stack exec command_name`: run this command in stack

### Notes

The easiest way to run a project is with `stack exec` after building it. But while developing, you don't want to build every time you want to check your changes. So the easiest way to run at that point is with `stack ghci`. Then run the function you're building. Every time you make a change, you can just reload the file you're working with and run your function again.

Here are some useful shortcuts in the ghci repl:

- `:q`: get out of the repl :)
- `:t something`: get the type of something
- `:l some/file.hs`: load a file into the repl context
- `:h`: a list of all the commands you can run in ghci

Try the following snippet
```haskell
stack ghci

let test = "some test"
test
:t test

let test2 a b = a + b
:t test2
test2 4 5
test2 -- should error, it's alright

print it
print -- should error, it's alright

:q
```
