# qpid-cpp

## Building sources

```
PS C:\Users\mg\Downloads\qpid-cpp-1.39.0\build> cmake ..
-- Building for: Visual Studio 16 2019
-- The C compiler identification is MSVC 19.22.27905.0
-- The CXX compiler identification is MSVC 19.22.27905.0
-- Check for working C compiler: C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.22.27905/bin/Hostx86/x86/cl.exe
-- Check for working C compiler: C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.22.27905/bin/Hostx86/x86/cl.exe -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.22.27905/bin/Hostx86/x86/cl.exe
...
-- Found PythonInterp: D:/FILES/TOOLS/python-3.7.4-embed-amd64/python.exe (found version "3.7.4")
  File "<string>", line 1
    from distutils.sysconfig import get_python_lib; print get_python_lib(False, prefix='C:/Program Files (x86)/qpid-cpp').replace('\\', '/')
                                                                       ^
SyntaxError: invalid syntax
CMake Error at managementgen/CMakeLists.txt:34 (install):
  install DIRECTORY given no DESTINATION!


-- Could NOT find PkgConfig (missing: PKG_CONFIG_EXECUTABLE)
-- Could NOT find Ruby (missing: RUBY_EXECUTABLE RUBY_INCLUDE_DIR RUBY_LIBRARY)
-- Could NOT find Doxygen (missing: DOXYGEN_EXECUTABLE)
-- Could NOT find VALGRIND (missing: VALGRIND_EXECUTABLE)
-- Could NOT find CyrusSASL (missing: CYRUS_SASL_LIBRARY CYRUS_SASL_INCLUDE_DIR)
CMake Error at src/CMakeLists.txt:87 (message):
  Can't locate ruby, needed to generate amqp 0-10 framing code.
  
  -- Configuring incomplete, errors occurred!
See also "C:/Users/mg/Downloads/qpid-cpp-1.39.0/build/CMakeFiles/CMakeOutput.log".
```

## Building required packages

### Python

```
PS C:\Users\mg\Downloads\cpython-2.7.16\PCbuild> .\build.bat -h

Build CPython from the command line.  Requires the appropriate
version(s) of Microsoft Visual Studio to be installed (see readme.txt).

After the flags recognized by this script, up to 9 arguments to be passed
directly to MSBuild may be passed.  If the argument contains an '=', the
entire argument must be quoted (e.g. `build.bat "/p:PlatformToolset=v100"`).
Alternatively you can put extra flags for MSBuild in a file named
will be picked automatically by MSBuild. Flags put in this file does not
need to be quoted. You can still use environment variables inside the
response file.

Available flags:
  -h  Display this help message
  -r  Target Rebuild instead of Build
  -d  Set the configuration to Debug
      Extension modules that depend on external libraries will not attempt
      to build if this flag is not present
  -m  Enable parallel build
  -M  Disable parallel build (disabled by default)
  -v  Increased output messages
  -k  Attempt to kill any running Pythons before building (usually done
      automatically by the pythoncore project)
  --pgo          Build with Profile-Guided Optimization.  This flag
                 overrides -c and -d

Available flags to avoid building certain modules.
These flags have no effect if '-e' is not given:
  --no-ssl      Do not attempt to build _ssl
  --no-tkinter  Do not attempt to build Tkinter
  --no-bsddb    Do not attempt to build _bsddb

Available arguments:
  -c Release | Debug | PGInstrument | PGUpdate
     Set the configuration (default: Release)
  -p x64 | Win32
     Set the platform (default: Win32)
  -t Build | Rebuild | Clean | CleanAll
     Set the target manually
  --pgo-job  The job to use for PGO training; implies --pgo
             (default: "-m test.regrtest --pgo")
PS C:\Users\mg\Downloads\cpython-2.7.16\PCbuild> .\build.bat -p x64 -t Build
Build environments: x86, amd64, x86_amd64

The system cannot find the path specified.
The system cannot find the path specified.
```

## Powershell script for automating the building
