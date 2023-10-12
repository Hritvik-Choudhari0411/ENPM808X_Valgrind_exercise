# Valgrind Exercise

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```

### What happens when the executable is linked statically?  Does Valgrind still detect those same bugs?

- Because of differences in the execution environment, Valgrind's coverage and capabilities may differ when used with statically linked executables compared to dynamically linked ones. When an executable is linked statically, Valgrind can still detect memory-related issues within the program's code, but it may be less effective at identifying issues related to external or system libraries, and it may produce false positives or false negatives due to these differences.
