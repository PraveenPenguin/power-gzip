POWER9 NX zlib compliant software (under construction)

## How to Use
### If want to use nxzlib to substitue zlib, following the steps as below:    
1. Build libnxz.so
```
make clean; make
```
2. Use libnxz.so to substitute libz.so    
```
cp libnxz.so /usr/lib/libnxz.so
mv /usr/lib/libz.so /usr/lib/libz.so.bak
ln -s /usr/lib/libnxz.so /usr/lib/libz.so
```
If don't want to override the libz.so, use LD_PRELOAD to run. Something like:    
```
LD_PRELOAD=./libnxz.so /home/your_pragram
```
    
### If want to use nxzlib standalone, following the steps as below:
1. Edit Makefile and remove line "ZLIB = -DZLIB_API"
2. Build libnxz.so
```
make clean; make
```

## Supported Functions List
Currently, supported the following functions.  
If want to use libnxz standalone, add a prefix 'nx_' before the function.  

- compress
- compress2
- compressBound
- uncompress
- uncompress2
     
- inflateInit_
- inflateInit2_
- inflateEnd
- inflate
    
- deflateInit_
- deflateInit2_
- deflateEnd
- deflate

