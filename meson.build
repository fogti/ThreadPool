project('ThreadPool', ['cpp'],
    license : 'Zlib',
    default_options : ['cpp_std=c++17'])

threads_dep = dependency('threads')
pkgg = import('pkgconfig')
inc = include_directories('.')

lib = library('ThreadPool',
    'ThreadPool.cxx',
    'ThreadPool.hpp',
    dependencies : [threads_dep],
    include_directories : inc,
    install : true)

install_headers('ThreadPool.hpp')

pkgg.generate(lib)

threadpool_dep = declare_dependency(link_with : lib, include_directories : inc)
