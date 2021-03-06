### inception_cmake: CMake Tensorflow Serving Client
These are my hacks around getting a Tensorflow Serving client (using the tutorial `inception_client.cc`) in C++ built via CMake. There's a few changes in the CMake submodules to let me invoke the protobuf compiler to support the *.proto file layout that exists in the `tensorflow/serving` repository. This checks out the `serving` submodule to the official repository and moves the CMakeLists.txt file out. This assumes the following have been installed:

1. Protobuf (version `3.5.2`)
2. gRPC (version `1.14.0`)
3. Tensorflow (version `1.6.0`)


### Build
If this is the first time, make sure to fetch the submodule files
```bash
git submodule update --init --recursive
cd serving
git clone --recursive https://github.com/tensorflow/tensorflow.git -b v1.6.0
cd ..
```

```bash
mkdir build && cd build
cmake ..
make
```
