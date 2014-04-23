build-fat-library
=================

Utility for building libraries as fat .a files for iOS projects

Example
=======
Build libpng as a fat .a library for iPhone Simulator (i386), and iPhone/iPad (armv7 and armv7s)

$ sh build-fat-library -j4 -l .libs libpng-1.6.10/

The -l flag tells the script to look for the build library in .libs/. The default is lib/.
The resulting fat lib is placed in fat-lib/

$ file libpng-1.6.10/fat-lib/libpng16.a
libpng-1.6.10/fat-lib/libpng16.a: Mach-O universal binary with 3 architectures
libpng-1.6.10/fat-lib/libpng16.a (for architecture i386):	current ar archive random library
libpng-1.6.10/fat-lib/libpng16.a (for architecture armv7):	current ar archive random library
libpng-1.6.10/fat-lib/libpng16.a (for architecture armv7s):	current ar archive random library
