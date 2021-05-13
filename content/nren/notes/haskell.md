+++
title = "Stack (Haskell) Notes"
date = 2019-06-29T10:46:03Z
draft = true
+++

Direct ghc access with the following form (here getting the version):
```
stack exec -- ghc --version
```

run as a script:
```
stack runghc -- meep.hs

# include packages in scripts
stack runghc --package package-name -- meep.hs

```
Dont forget to make executable ```chmod +x meep.hs```
To make scripting more sharable the [script interpreter feature](https://docs.haskellstack.org/en/stable/GUIDE/#script-interpreter) can be used to set the GHC version

```Haskell
#!/usr/bin/env stack
-- stack --resolver lts-12.21 script

main :: IO ()
main = undefined
```

> note the shebang means the script can be run with ```./meep.hs``` 
> for more on scripts see this blogpost on [bitrot free scripts](https://www.fpcomplete.com/blog/2016/08/bitrot-free-scripts/)

### Using stack (from [user guide](https://docs.haskellstack.org/en/stable/GUIDE/#user-guide))
```
stack new my-project
cd my-project
stack setup
stack build
stack exec my-project-exe
```

### Dependencies

Add to ```package.yaml``` under dependencies:
```
dependencies:
- base >= 4.7 && < 5
- text # added here
```

See dependencies that were installed : ``` stack ls dependencies ```

If it says that it was unable to construct the build plan, check out this section on [currated package sets](https://docs.haskellstack.org/en/stable/GUIDE/#curated-package-sets).

```stack clean``` deletes the local working directories containing compiler output. By default, that means the contents of directories in .stack-work/dist, for all the .stack-work directories within a project.

```stack purge``` deletes the local stack working directories, including extra-deps, git dependencies and the compiler output (including logs). It does not delete any snapshot packages, compilers or programs installed using stack install. This essentially reverts the project to a completely fresh state, as if it had never been built. stack purge is just a shortcut for ```stack clean --full```

__GHCI REPL:__

```stack ghci```

___Or run tests:__

```stack test```