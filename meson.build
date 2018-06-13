project('ThreadPool', ['cpp'], default_options : ['cpp_std=c++17'])

threads_dep = dependency('threads')

test('Example', executable('example', sources : ['example.cpp'], dependencies : [threads_dep]))

install_headers('ThreadPool.hpp')
