build-fat-library
=================

Utility for building libraries as fat .a files for iOS projects

This script executes a ./configure and make sequence to build a library three times for three architectures for iOS projects. Then, it combines the resulting libraries into one fat archive.

Example
=======
Build libpng as a fat .a library for iPhone Simulator (i386), and iPhone/iPad (armv7 and armv7s)

Run this command from outside the libpng src folder.

```bash
$ sh build-fat-library -j4 -l .libs libpng-1.6.10/
```

The final argument is the name of the source folder to build in.
Because the libpng build process places libpng16.a in libpng-1.6.10/.libs, the -l flag tells the script to look there for the resulting build library. The default is lib/.
The resulting fat lib is placed in fat-lib/

```bash
$ file libpng-1.6.10/fat-lib/libpng16.a
libpng-1.6.10/fat-lib/libpng16.a: Mach-O universal binary with 3 architectures
libpng-1.6.10/fat-lib/libpng16.a (for architecture i386):	current ar archive random library
libpng-1.6.10/fat-lib/libpng16.a (for architecture armv7):	current ar archive random library
libpng-1.6.10/fat-lib/libpng16.a (for architecture armv7s):	current ar archive random library
```
