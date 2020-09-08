# gcc-i686-posix-sjlj-for-MSYS

$ export CPP=/mingw/bin/cpp \
export LD_LIBRARY_PATH=/usr/local/lib \
export LIBS= \
export   CFLAGS='-O2 -pipe -fno-ident -I/usr/local/include -I/usr/mingw/i686-w64-mingw32/include' \
export CPPFLAGS='-O2 -pipe -fno-ident -I/usr/local/include -I/usr/mingw/i686-w64-mingw32/include' \
export CXXFLAGS='-O2 -pipe -fno-ident -I/usr/local/include -I/usr/mingw/i686-w64-mingw32/include' \
export  LDFLAGS='-pipe -fno-ident -L/usr/local/lib  -L/usr/mingw/i686-w64-mingw32/lib -Wl,--large-address-aware' 

mkdir gccbuild
cd gccbuild

../gcc-10/configure --prefix=/mingw32 --with-local-prefix=/mingw32 --build=i686-w64-mingw32 --host=i686-w64-mingw32 --target=i686-w64-mingw32 --with-native-system-header-dir=/mingw32/i686-w64-mingw32/include --libexecdir=/mingw32/libexec --enable-checking=release --enable-fully-dynamic-string --enable-graphite --enable-languages=c,lto,c++ --enable-libatomic --enable-libgomp --enable-libstdcxx-time=yes --enable-lto --enable-sjlj-exceptions --enable-shared --enable-static --enable-threads=posix --enable-libssp --disable-64bit --disable-bootstrap --disable-isl-version-check --disable-libstdcxx-debug --disable-libstdcxx-pch --disable-multilib --disable-nls --disable-rpath --disable-symvers --disable-werror --disable-win32-registry --with-arch=i686 --with-gmp=/usr/local --with-gnu-as --with-gnu-ld --with-isl=/usr/local --with-libiconv --with-mpc=/usr/local --with-mpfr=/usr/local --with-system-zlib

make -j2 && echo -------------.install.-------------------------- && make install

gcc -v
Using built-in specs.
COLLECT_GCC=gcc
Target: i686-w64-mingw32
Configured with: ../gcc-10/configure --prefix=/mingw32 --with-local-prefix=/mingw32 --build=i686-w64-mingw32 --host=i686-w64-mingw32 --target=i686-w64-mingw32 --with-native-system-header-dir=/mingw32/i686-w64-mingw32/include --libexecdir=/mingw32/libexec --enable-checking=release --enable-fully-dynamic-string --enable-graphite --enable-languages=c,lto,c++ --enable-libatomic --enable-libgomp --enable-libstdcxx-time=yes --enable-lto --enable-sjlj-exceptions --enable-shared --enable-static --enable-threads=posix --enable-libssp --disable-64bit --disable-bootstrap --disable-isl-version-check --disable-libstdcxx-debug --disable-libstdcxx-pch --disable-multilib --disable-nls --disable-rpath --disable-symvers --disable-werror --disable-win32-registry --with-arch=i686 --with-gmp=/usr/local --with-gnu-as --with-gnu-ld --with-isl=/usr/local --with-libiconv --with-mpc=/usr/local --with-mpfr=/usr/local --with-system-zlib
Thread model: posix
Supported LTO compression algorithms: zlib zstd
gcc version 10.2.1 20200907 (GCC)
