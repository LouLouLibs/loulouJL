# "Private" registry  

For utilities that probably should not make their way to the julia general registry.

## Create a registry

```julia
using LocalRegistry
create_registry("loulouJL", 
    "git@github.com:LouLouLibs/loulouJL.git";
    description = "Registry for sharing personal packages and utilities", 
    push = true, 
    branch = "main")
```


## Add a package to this registry

```julia
# inside package folder ... activate package
using LocalRegistry
register(registry="git@github.com:LouLouLibs/loulouJL.git", push=true)
```


## Add registry to julia install

```julia
pkg"registry add https://github.com/LouLouLibs/loulouJL.git"

```
