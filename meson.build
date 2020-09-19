project('ThreadPool', ['cpp'],
    license : 'Zlib',
    default_options : ['cpp_std=c++17'])

threads_dep = dependency('threads')
pkgg = import('pkgconfig')

lib = static_library('ThreadPool',
    'ThreadPool.cxx',
    'ThreadPool.hpp',
    dependencies : [threads_dep],
    pic : true,
    install : true)

install_headers('ThreadPool.hpp')

pkgg.generate(lib)

inc = include_directories('.')
threadpool_dep = declare_dependency(link_with : lib, include_directories : inc)
