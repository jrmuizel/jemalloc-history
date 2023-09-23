This was built with the following commands

```
git clone https://github.com/freebsd/freebsd-src
cd freebsd-src
git reset --hard d7ba3e423a9a2ef65b371e1dffcdf9217b485948
git filter-repo --force --path  lib/libc/stdlib/malloc.c --path lib/libc/stdlib/malloc.3 --path lib/libc/stdlib/rb.h
git checkout --orphan trunc a7ca0a3d409c0004ec5067b59fe409c6d8951706
git commit -c a7ca0a3d409c0004ec5067b59fe409c6d8951706
git rebase  --onto trunc a7ca0a3d409c0004ec5067b59fe409c6d8951706 main
```

It can be grafted into the jemalloc repo with
```
git fetch https://github.com/jrmuizel/jemalloc-history
git replace --graft 289053c95bff45e69c8310aea82f1b8550c2a996 9592e2aa8c9f0d603f1dbf13c489d6418e077369
```
