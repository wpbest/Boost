# Boost 
Boost library for Windows 10 UWP Applications

Supported Components:

    - atomic                   : building
    - chrono                   : building
    - container                : not building
    - context                  : building
    - coroutine                : not building
    - date_time                : building
    - exception                : not building
    - filesystem               : not building
    - graph                    : not building
    - graph_parallel           : not building
    - iostreams                : building
    - locale                   : not building
    - log                      : not building
    - math                     : not building
    - mpi                      : not building
    - program_options          : not building
    - python                   : not building
    - random                   : not building
    - regex                    : not building
    - serialization            : building
    - signals                  : building
    - system                   : building
    - test                     : not building
    - thread                   : building
    - timer                    : not building
    - wave                     : not building


Defines for your projects using Boost.

BOOST_NO_AUTOLINK

BOOST_ALL_DYN_LINK

I had to define BOOST_NO_AUTOLINK to disable the auto link feature in Boost. If there is a better solution please let me know.

You will need to define BOOST_ALL_DYN_LINK in the projects using Boost with external constants. i.e. boost_zlib

Build Boost with a command line

Assuming the git repository is located at C:\git\Boost

Build the Boost build tool b2 and then build the Boost library (x86:Debug)

bootstrap.bat

b2 -s ZLIB_SOURCE=C:\git\Boost\zlib -q --without-context --without-graph --without-math --without-mpi --without-python --without-wave --without-log --without-container --without-coroutine --without-coroutine2 --without-exception --without-filesystem --without-graph_parallel --without-locale --without-program_options --without-random --without-regex --without-timer --without-test --without-type_erasure --stagedir=stage_x86 --toolset=msvc-14.0 --build-type=complete architecture=x86 address-model=32 stage variant=debug threading=multi link=shared

The windows-api=store seems to not be supported under Windows 10 UWP applications. If there is a better solution please let me know.

Output binary are located in stage_x86\lib 

Build Boost with Visual Studio 2015 Update 1

build\visualstudio\solutions\boost.uwp\boost.uwp.sln

