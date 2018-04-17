project('ThreadPool', ['cpp'], default_options : ['cpp_std=c++17'])

threads_dep = dependency('threads')

executable('example', sources : ['example.cpp'], dependencies : [threads_dep],
           include_directories : [include_directories('subprojects/function2/include')])

install_headers('ThreadPool.h')
