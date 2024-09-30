This is a port of the **mtree** port from archiecobbs/mtree-port:master; however, it has modifications to compile on recent Linux kernels (6.1.0-22) as well as MacOS (22.6.0).
The changes are specific to create.c and compare.c and look for #ifdef __linux__, such as:

#ifdef __linux__
    if ((s->st_mtimespec.tv_sec != p->fts_statp->st_mtim.tv_sec) ||
        (s->st_mtimespec.tv_nsec != p->fts_statp->st_mtim.tv_nsec)) {
#else
    if ((s->st_mtimespec.tv_sec != p->fts_statp->st_mtimespec.tv_sec) ||
        (s->st_mtimespec.tv_nsec != p->fts_statp->st_mtimespec.tv_nsec)) {
#endif


This project is a port of the very useful **mtree** utility, originally only available in BSD distributions, to Linux and other operating systems.

The **mtree** utility compares the file hierarchy rooted in the current directory against a specification read from the standard input. Messages are written to the standard output for any files whose characteristics do not match the specifications, or which are missing from either the file hierarchy or the specification.

This port of **mtree** uses the `autoconf` infrastructure to maintain portability.

See the [ManPages](https://github.com/archiecobbs/mtree-port/wiki/ManPages) for details on usage, and [Downloads](https://github.com/archiecobbs/mtree-port/wiki/Downloads) for where to get it.
