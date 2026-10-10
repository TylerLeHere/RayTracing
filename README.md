# Ray Tracing

This is a personal learning project based on [*Ray Tracing in One Weekend*](https://raytracing.github.io/books/RayTracingInOneWeekend.html). I built it to learn the basics of ray tracing and experiment with creating images.


## Build and Run

All output (the program and the image) goes in `build/`.

**First time** (or after deleting `build/`):

```sh
cmake -B build
```

**After editing code**, from inside `build/`:

```sh
cd build
make                          # compile
./raytracer > image.ppm       # render the image
open -a Preview image.ppm     # view it (VS Code shows .ppm as text)
```

Or in one line from the project root:

```sh
cmake --build build && ./build/raytracer > build/image.ppm && open -a Preview build/image.ppm
```

**Faster renders** (optimized build):

```sh
cmake -B build-release -DCMAKE_BUILD_TYPE=Release
cmake --build build-release
./build-release/raytracer > build-release/image.ppm
```

**Adding a `.cpp` file:** list it in `add_executable` in `CMakeLists.txt`, then run `make` again. Headers don't need to be listed.

**Fresh start:** `rm -rf build && cmake -B build`
