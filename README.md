# openblas-benchmark-m1
Benchmarking OpenBLAS on an Apple MacBook M1 w/ 16GB RAM. 

In order to compile the benchmark's using the native MacOS LLVM, you will need to have native homebrew for the M1 and install gfortran. Modify the Makefile as follows, where `-L` points to your homebrew `lib` path:
```
smallscaling: smallscaling.c ../$(LIBNAME)
        $(CC) $(CFLAGS) -o $(@F) $^ $(EXTRALIB) -Xpreprocessor -fopenmp -lomp -lm -lpthread -L /opt/homebrew/lib/
```
