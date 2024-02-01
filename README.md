## C# With CMake Example

How to build a WPF app & WinForms app with CMake in .NET 6+

## Build
```
# Create a build directory and build using CMake in the root dir
mkdir build && cd build
cmake ..

# Build and restore NuGet packages needed to build 
cmake --build . -- -r

```
