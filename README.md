# ThreadPool [![pipeline status](https://gitlab.com/jhasse/ThreadPool/badges/master/pipeline.svg)](https://gitlab.com/jhasse/ThreadPool/commits/master)

A simple C++17 Thread Pool implementation.
This library uses `meson` as the build system and installs a library + `pkg-config`-file.

Basic usage:
```c++
// create thread pool with 4 worker threads
ThreadPool pool(4);

// enqueue and store future
auto result = pool.enqueue([](int answer) { return answer; }, 42);

// get result from future
std::cout << result.get() << std::endl;

```

Simple example program:
```c++
#include <iostream>
#include <vector>
#include <chrono>

#include "ThreadPool.hpp"

int main()
{
    ThreadPool pool(4);
    std::vector< std::future<int> > results;

    for(int i = 0; i < 8; ++i) {
        results.emplace_back(
            pool.enqueue([i] {
                std::cout << "hello " << i << std::endl;
                std::this_thread::sleep_for(std::chrono::seconds(1));
                std::cout << "world " << i << std::endl;
                return i*i;
            })
        );
    }

    for(auto && result: results)
        std::cout << result.get() << ' ';
    std::cout << std::endl;

    return 0;
}
```
