## The Heirloom Project

This is a mirror of [The Heirloom Project](http://heirloom.sourceforge.net) CVS repositories— a collection 
of hisorical UNIX tools,principally derived from System V, which have been patched to build on a modern system.

Particularly noteworthy are its historical Bourne shell, toolchain, and source code management tools. It includes 
some of the original implementations of m4, lex, yacc, SCCS, troff, etc. Also included here are the related 
original [vi](http://ex-vi.sourceforge.net)  and [nail](http://heirloom.sourceforge.net/mailx.html) (mailx) 
repositories.

### Changes:
* After encountering cpio errors and researching the cause, [this page](https://www.virtualbox.org/wiki/SolarisCrossCompiler) 
recommends the following changes:
`fix the call to open on line 1013 of libpkg/pkgtrans.c to open(tmp_file, O_RDWR, O_CREAT)`

`fix the cpio command lines in libpkg/pkgtrans.c lines 1151, 1164, 1595 and 1827 to remove the "-D"`

`fix the call to execl on line 180 of libpkg/runcmd.c to use "/bin/sh"`

`replace the sizeof (unsigned long) on line 328 of libpkg/verify.c to ucp += 4`

* pkgtrans.c and verify.c have been changed but runcmd.c still uses /sbin/sh

* Changed heirloom-devtools/make/bsd/bsd.cc to [not use auto as type specifier](https://www.illumos.org/rb/r/353/diff/1?expand=1#0)
* Changed "include<bsd/bsd.h>" to use the included bsd.h in heirloom-devtools/make/include/bsd for the following files:
heirloom-devtools/make/bsd/bsd.cc
heirloom-devtools/make/mksh/misc.cc
heirloom-devtools/make/src/main.cc
heirloom-devtools/make/src/misc.cc
* Changed vi/ex_re.c to use heirloom/libcommon/regexp.h

