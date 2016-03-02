Repro for https://github.com/commercialhaskell/stack/issues/1864

Error: `/usr/bin/ar: dist/build/test.p_o: No such file or directory`

# Cabal repro

Requirements: have `Cabal-1.22.7.0` (or potentially some other version after
`Cabal-1.22.4.0`, which doesn't appear to have this issue)

```
runhaskell Setup.hs configure
runhaskell Setup.hs build
runhaskell Setup.hs configure --enable-library-profiling
runhaskell Setup.hs build
```

# Stack repro

```
stack build
stack build --library-profiling
```
