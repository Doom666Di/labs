┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ pushd .
~/Doom666Di/workspace ~/Doom666Di/workspace
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ source scripts/activate       
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ git clone https://github.com/${GITHUB_USERNAME}/lab02.git projects/lab03
Cloning into 'projects/lab03'...
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 16 (delta 0), reused 13 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (16/16), done.
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ cd projects/lab03
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git remote remove origin
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab03.git
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ g++ -std=c++11 -I./include -c sources/print.cpp
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ ls print.o  
print.o
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ nm print.o | grep print
0000000000000000 T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSo
0000000000000026 T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSt14basic_ofstreamIcS2_E
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ ar rvs print.a print.o
ar: creating print.a
a - print.o
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ file print.a
print.a: current ar archive
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ g++ -std=c++11 -I./include -c examples/example1.cpp
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ ls example1.o
example1.o
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ g++ example1.o print.a -o example1                 
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ ./example1 && echo
hello
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ g++ -std=c++11 -I./include -c examples/example2.cpp
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ nm example2.o
0000000000000000 V DW.ref.__gxx_personality_v0
                 U __gxx_personality_v0
0000000000000000 T main
                 U _Unwind_Resume
                 U _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSt14basic_ofstreamIcS2_E
                 U _ZNSt14basic_ofstreamIcSt11char_traitsIcEEC1EPKcSt13_Ios_Openmode
                 U _ZNSt14basic_ofstreamIcSt11char_traitsIcEED1Ev
0000000000000000 W _ZNSt15__new_allocatorIcED1Ev
0000000000000000 W _ZNSt15__new_allocatorIcED2Ev
0000000000000000 n _ZNSt15__new_allocatorIcED5Ev
                 U _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEC1EPKcRKS3_
                 U _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEED1Ev
                 U _ZSt21ios_base_library_initv
0000000000000000 r _ZStL19piecewise_construct
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ g++ example2.o print.a -o example2
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ ./example2
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cat log.txt && echo
hello
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ rm -rf example1.o example2.o print.o
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ rm -rf print.a
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ rm -rf example1 example2
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ rm -rf log.txt
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(print)
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cat >> CMakeLists.txt <<EOF
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cat >> CMakeLists.txt <<EOF
add_library(print STATIC \${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$  cat >> CMakeLists.txt <<EOF
include_directories(\${CMAKE_CURRENT_SOURCE_DIR}/include)
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cmake -H. -B_build
Command 'cmake' not found, but can be installed with:
sudo apt install cmake
Do you want to install it? (N/y)y
sudo apt install cmake
[sudo] password for kali: 
Package cmake is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

Error: Package 'cmake' has no installation candidate
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ sudo apt-get update -y
Get:1 http://kali.download/kali kali-rolling InRelease [41.5 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 Packages [20.6 MB]
Get:3 http://kali.download/kali kali-rolling/main amd64 Contents (deb) [49.1 MB]
Get:4 http://kali.download/kali kali-rolling/contrib amd64 Packages [115 kB]                                     
Get:5 http://kali.download/kali kali-rolling/contrib amd64 Contents (deb) [267 kB]                               
Get:6 http://kali.download/kali kali-rolling/non-free amd64 Packages [202 kB]                                    
Get:7 http://kali.download/kali kali-rolling/non-free amd64 Contents (deb) [884 kB]                              
Get:8 http://kali.download/kali kali-rolling/non-free-firmware amd64 Packages [10.8 kB]                          
Get:9 http://kali.download/kali kali-rolling/non-free-firmware amd64 Contents (deb) [24.3 kB]                    
Fetched 71.2 MB in 13s (5,364 kB/s)                                                                              
Reading package lists... Done
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ sudo apt-get update   
Hit:1 http://http.kali.org/kali kali-rolling InRelease
Reading package lists... Done
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ sudo apt-get install cmake
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  cmake-data libjsoncpp26 librhash1
Suggested packages:
  cmake-doc cmake-format elpa-cmake-mode ninja-build
The following NEW packages will be installed:
  cmake cmake-data libjsoncpp26 librhash1
0 upgraded, 4 newly installed, 0 to remove and 1505 not upgraded.
Need to get 13.8 MB of archives.
After this operation, 52.4 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://kali.download/kali kali-rolling/main amd64 cmake-data all 3.30.5-1 [2,223 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 libjsoncpp26 amd64 1.9.6-3 [81.7 kB]
Get:3 http://kali.download/kali kali-rolling/main amd64 librhash1 amd64 1.4.5-1 [132 kB]
Get:4 http://kali.download/kali kali-rolling/main amd64 cmake amd64 3.30.5-1 [11.4 MB]
Fetched 13.8 MB in 3s (4,009 kB/s)
Selecting previously unselected package cmake-data.
(Reading database ... 400936 files and directories currently installed.)
Preparing to unpack .../cmake-data_3.30.5-1_all.deb ...
Unpacking cmake-data (3.30.5-1) ...
Selecting previously unselected package libjsoncpp26:amd64.
Preparing to unpack .../libjsoncpp26_1.9.6-3_amd64.deb ...
Unpacking libjsoncpp26:amd64 (1.9.6-3) ...
Selecting previously unselected package librhash1:amd64.
Preparing to unpack .../librhash1_1.4.5-1_amd64.deb ...
Unpacking librhash1:amd64 (1.4.5-1) ...
Selecting previously unselected package cmake.
Preparing to unpack .../cmake_3.30.5-1_amd64.deb ...
Unpacking cmake (3.30.5-1) ...
Setting up libjsoncpp26:amd64 (1.9.6-3) ...
Setting up cmake-data (3.30.5-1) ...
Setting up librhash1:amd64 (1.4.5-1) ...
Setting up cmake (3.30.5-1) ...
Processing triggers for libc-bin (2.40-3) ...
Processing triggers for man-db (2.13.0-1) ...
Processing triggers for kali-menu (2024.4.0) ...
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cmake -H. -B_build
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is GNU 14.2.0
-- The CXX compiler identification is GNU 14.2.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done (0.5s)
-- Generating done (0.0s)
-- Build files have been written to: /home/kali/Doom666Di/workspace/projects/lab03/_build
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cmake --build _build
[ 50%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[100%] Linking CXX static library libprint.a
[100%] Built target print
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cat >> CMakeLists.txt <<EOF

add_executable(example1 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example1.cpp)
add_executable(example2 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example2.cpp)
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cat >> CMakeLists.txt <<EOF

target_link_libraries(example1 print)
target_link_libraries(example2 print)
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cmake --build _build
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/kali/Doom666Di/workspace/projects/lab03/_build
[ 33%] Built target print
[ 50%] Building CXX object CMakeFiles/example1.dir/examples/example1.cpp.o
[ 66%] Linking CXX executable example1
[ 66%] Built target example1
[ 83%] Building CXX object CMakeFiles/example2.dir/examples/example2.cpp.o
[100%] Linking CXX executable example2
[100%] Built target example2
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cmake --build _build --target print
[100%] Built target print
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cmake --build _build --target example1
[ 50%] Built target print
[100%] Built target example1
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cmake --build _build --target example2
[ 50%] Built target print
[100%] Built target example2
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ ls -la _build/libprint.a
-rw-rw-r-- 1 kali kali 2110 Mar 10 14:59 _build/libprint.a
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ _build/example1 && echo
hello
hello
Command 'hello' not found, but can be installed with:
sudo apt install hello            
sudo apt install hello-traditional
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ _build/example1 && echo
hello
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ _build/example2
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cat log.txt && echo
hello
hello
Command 'hello' not found, but can be installed with:
sudo apt install hello            
sudo apt install hello-traditional
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cat log.txt && echo
hello
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ rm -rf log.txt
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git clone https://github.com/tp-labs/lab03 tmp
Cloning into 'tmp'...
remote: Enumerating objects: 91, done.
remote: Counting objects: 100% (30/30), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 91 (delta 23), reused 21 (delta 21), pack-reused 61 (from 1)
Receiving objects: 100% (91/91), 1.02 MiB | 2.92 MiB/s, done.
Resolving deltas: 100% (41/41), done.
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ mv -f tmp/CMakeLists.txt .
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ rm -rf tmp
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cat CMakeLists.txt 
cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

option(BUILD_EXAMPLES "Build examples" OFF)

project(print)

add_library(print STATIC ${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)

target_include_directories(print PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>
)

if(BUILD_EXAMPLES)
  file(GLOB EXAMPLE_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/examples/*.cpp")
  foreach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
    get_filename_component(EXAMPLE_NAME ${EXAMPLE_SOURCE} NAME_WE)
    add_executable(${EXAMPLE_NAME} ${EXAMPLE_SOURCE})
    target_link_libraries(${EXAMPLE_NAME} print)
    install(TARGETS ${EXAMPLE_NAME}
      RUNTIME DESTINATION bin
    )
  endforeach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
endif()

install(TARGETS print
    EXPORT print-config
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
)

install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/ DESTINATION include)
install(EXPORT print-config DESTINATION cmake)
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/kali/Doom666Di/workspace/projects/lab03/_build
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ cmake --build _build --target install
[100%] Built target print
Install the project...
-- Install configuration: ""
-- Installing: /home/kali/Doom666Di/workspace/projects/lab03/_install/lib/libprint.a
-- Installing: /home/kali/Doom666Di/workspace/projects/lab03/_install/include
-- Installing: /home/kali/Doom666Di/workspace/projects/lab03/_install/include/print.hpp
-- Installing: /home/kali/Doom666Di/workspace/projects/lab03/_install/cmake/print-config.cmake
-- Installing: /home/kali/Doom666Di/workspace/projects/lab03/_install/cmake/print-config-noconfig.cmake
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ tree _install
_install
├── cmake
│   ├── print-config.cmake
│   └── print-config-noconfig.cmake
├── include
│   └── print.hpp
└── lib
    └── libprint.a

4 directories, 4 files
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git add CMakeLists.txt
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git commit -m"added CMakeLists.txt"
[main 80a6fb5] added CMakeLists.txt
 1 file changed, 36 insertions(+)
 create mode 100644 CMakeLists.txt
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git push origin master
error: src refspec master does not match any
error: failed to push some refs to 'https://github.com/Doom666Di/lab03.git'
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git push origin main  
Username for 'https://github.com': Doom666Di
Password for 'https://Doom666Di@github.com': 
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/Doom666Di/lab03.git/'
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git push origin main
Username for 'https://github.com': Doom666Di
Password for 'https://Doom666Di@github.com': 
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/Doom666Di/lab03.git/'
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git push origin main                    
Username for 'https://github.com': Doom666Di
Password for 'https://Doom666Di@github.com': 
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/Doom666Di/lab03.git/'
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git push origin main
Username for 'https://github.com': Doom666Di
Password for 'https://Doom666Di@github.com': 
remote: Repository not found.
fatal: repository 'https://github.com/Doom666Di/lab03.git/' not found
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab03]
└─$ git push origin main
Username for 'https://github.com': Doom666Di
Password for 'https://Doom666Di@github.com': 
Enumerating objects: 19, done.
Counting objects: 100% (19/19), done.
Delta compression using up to 4 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (19/19), 2.75 KiB | 2.75 MiB/s, done.
Total 19 (delta 1), reused 15 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/Doom666Di/lab03.git
 * [new branch]      main -> main
