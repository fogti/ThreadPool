project('ThreadPool', ['cpp'], default_options : ['cpp_std=c++17'])

threads_dep = dependency('threads')

lib = static_library('ThreadPool', 'ThreadPool.cpp')

install_headers('ThreadPool.hpp')

inc = include_directories('.')
threadpool_dep = declare_dependency(include_directories : inc, link_with : lib)
