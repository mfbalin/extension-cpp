# C++/CUDA Extensions in PyTorch

An example of writing a C++ extension for PyTorch. See
[here](http://pytorch.org/tutorials/advanced/cpp_extension.html) for the accompanying tutorial.

There are a few "sights" you can metaphorically visit in this repository:

- Inspect the C++ and CUDA extensions in the `cpp/` and `cuda/` folders,
- Build C++ and/or CUDA extensions by going into the `cpp/` or `cuda/` folder and executing `python setup.py install`,
- JIT-compile C++ and/or CUDA extensions by going into the `cpp/` or `cuda/` folder and calling `python jit.py`, which will JIT-compile the extension and load it,
- Benchmark Python vs. C++ vs. CUDA by running `python benchmark.py {py, cpp, cuda} [--cuda]`,
- Run gradient checks on the code by running `python grad_check.py {py, cpp, cuda} [--cuda]`.
- Run output checks on the code by running `python check.py {forward, backward} [--cuda]`.

## Authors

[Peter Goldsborough](https://github.com/goldsborough)


# Note from mfbalin

https://pytorch.org/cppdocs/api/library_root.html contains the torch C++ API.

https://pytorch.org/docs/stable/index.html contains the torch python API.

For the data we need to keep for the cache, we can use a global variable for
now, I can show how to build a data structure and expose it to python after.

The C++ implementation is located in the `cpp/lltm.cpp` file.

To run:

pytorch needs to be installed.

Then:

```
cd cpp
pip install -e .
python ../benchmark.py
```