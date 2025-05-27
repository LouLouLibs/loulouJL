# "Private" registry

For utilities that probably should not make their way to the julia general registry.

## Create a registry

From a barebone repository; see [doc](https://github.com/GunnarFarneback/LocalRegistry.jl/blob/master/docs/create_registry.md).

```julia
using LocalRegistry
create_registry("loulouJL",
    "https://github.com/LouLouLibs/loulouJL.git";
    description = "Registry for sharing personal packages and utilities",
    push = true,
    branch = "main")
```


## Add a package to this registry

Inside a package folder ... activate the package and simply record it; see [doc](https://github.com/GunnarFarneback/LocalRegistry.jl/blob/master/docs/register.md
).

```julia
using LocalRegistry, Pkg
Pkg.activate(".")
# register to local clone of the registry repository
register(registry="/Users/loulou/Dropbox/projects_code/julia_packages/loulouJL", push=false)
# then edit Package.toml to switch git@github (ssh) to https: login
# then do not forget to push to the registry github repository
```


## Add registry to julia install

If you want to add this registry to your julia (do only once per julia install)

```julia
pkg"registry add https://github.com/LouLouLibs/loulouJL.git"
Pkg.update()
```

Check that it works

```julia
Pkg.Registry.status()
Pkg.add("BazerUtils")
Pkg.status("BazerUtils")
```


## Packages in this Registry

- [`BazerUtils.jl`](https://github.com/LouLouLibs/BazerUtils.jl)
- [`FinanceRoutines.jl`](https://github.com/LouLouLibs/FinanceRoutines.jl)
- [`TigerFetch.jl`](https://github.com/LouLouLibs/TigerFetch.jl)
