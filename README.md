#### both the below commands built the executable as expected
`go build -o mainmod ./mainmod`

`go build -o submod1 ./modules/submodule1/`

#### even when modfile is giving for submodule it is succesful
`go build -o submod1-with-modfile -modfile ./modules/submodule1/go.mod ./modules/submodule1/`

#### but when the modfile is given as input for the building mainmod it is giving error
`go build -o mainmod-with-modfile -modfile ./go.mod ./mainmod`

```
directory mainmod is contained in a module that is not one of the workspace modules listed in go.work.
You can add the module to the workspace using go work use .
```

*the above is successful when `./modules/submodule1` in `go.work` is commented*
