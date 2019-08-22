cmake_minimum_required(VERSION 3.12)
project(pylibmc)

set(CMAKE_CXX_STANDARD 14)

include_directories(src /Users/ben/.pyenv/versions/3.6.8/include/python3.6m /usr/local/opt/libmemcached/include)

set(PYTHON_LIBRARIES "/Users/ben/.pyenv/versions/3.6.8/lib/python3.6/config-3.6m-darwin/libpython3.6m.a")
set(MEMCACHED_LIBRARIES "/usr/local/opt/libmemcached/lib/libmemcached.dylib")

add_library(pylibmc SHARED
        src/_pylibmcmodule.c
        src/_pylibmcmodule.h
        src/pylibmc-version.h)

target_link_libraries(pylibmc ${PYTHON_LIBRARIES} ${MEMCACHED_LIBRARIES})
