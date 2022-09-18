# OpenTimer
OpenTimer is a new static timing analysis (STA) tool to help IC designers quickly verify the circuit timing. It is developed completely from the ground up using C++17 to efficiently support parallel and incremental timing.
Key features are:
* Industry standard format (.lib, .v, .spef, .sdc) support
* Graph- and path-based timing analysis
* Parallel incremental timing for fast timing closure
* Award-winning tools and golden timers in CAD Contests
# Compile OpenTimer
## System Requirements
OpenTimer is very self-contained and has very few dependencies. 
To compile OpenTimer, you need a C++17 compiler and currently support:

* GNU C++ Compiler v7.3 with -std=c++1z
* Clang C++ Compiler v6.0 with -std=c++17
In addition, you need a tcl shell interpreter:
* tclsh (most Unix/Linux/OSX distributions already include tclsh)
OpenTimer has been tested to run well on Linux distributions and MAC OSX.
## Build through CMake
We use CMake to manage the source and tests. We recommend using out-of-source build.
```
$ git clone https://github.com/OpenTimer/OpenTimer.git
$ cd OpenTimer
$ mkdir build
$ cd build
$ cmake ../
$ apt install cmake --classic (If it shows that cmake is not installed already)
$ make 
```
After successful build, you can find binaries and libraries in the folders ```bin and lib```, respectively.
## Run Tests
OpenTimer uses Doctest for unit tests and TAU15 benchmarks for integration/regression tests. These benchmarks are generated by an industry standard timer and are being used by many EDA researchers.
```
$ make test
```
# Get Started with OpenTimer
```
$ ./bin/ot-shell
```

![OpenTimer](https://user-images.githubusercontent.com/110485513/190913917-dcbde034-274a-463f-98d4-f24976c89d79.png)

# Design Philosophy
OpenTimer has a unique software architecture to efficiently enable parallel incremental timing. We draw two levers on performance and useability by grouping each timing operation to one of the three categories, builder, action, and accessor.


