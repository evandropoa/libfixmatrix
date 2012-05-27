Fixed point matrix library
==========================
![Header image](http://kapsi.fi/~jpa/stuff/pix/fixmatrixlogo.png)

Libfixmatrix is a matrix computation library for microcontrollers.
It is based on the [libfixmath](http://code.google.com/p/libfixmath/) library, which uses 16.16 bit fixed point values.
The main focus is processors without an FPU, such as ARM Cortex-M3.
The compiled size of the library is less than 5 kB, depending on optimization settings and processor.

The library includes all basic matrix operations, such as multiplication, addition and transposition.
Matrix equation solving (and matrix inversion) is implemented through [QR-decomposition](http://en.wikipedia.org/wiki/QR_decomposition).
Also [Cholesky decomposition](http://en.wikipedia.org/wiki/Cholesky_decomposition) is included.

To avoid complexity and dynamic memory allocations, all matrices are allocated a buffer with constant size, specified with parameter `FIXMATRIX_MAX_SIZE`.
This wastes some memory with matrices smaller than the maximum size, but allows more predictable memory usage.

Libfixmatrix is suited well for tasks involving small matrices (often less than 10x10):
[Kalman filters](http://en.wikipedia.org/wiki/Kalman_filter), [Transformation matrices](http://en.wikipedia.org/wiki/Transformation_matrix)
and solving [Systems of linear equations](http://en.wikipedia.org/wiki/System_of_linear_equations).