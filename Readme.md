## Run the program 

```bash
g++ --std=c++17 TaskScheduler.cpp -o TaskScheduler
MacBook-Air:task-scheduler anish$ ./TaskScheduler
```

```bash
ID: 1, Description: Write report, Priority: 2, Deadline: 2025-06-10
ID: 2, Description: Review code, Priority: 1
Executing: Write report (ID: 1)
Executing: Review code (ID: 2)
MacBook-Air:task-scheduler anish$ cat tasks.txt 
1|Write report|2|2025-06-10|completed
2|Review code|1|none|completed
#DEPENDENCIES
2->1
```

## Build and Run

- GTest Installer Script: https://gist.github.com/butuzov/e7df782c31171f9563057871d0ae444a

```bash

CMake Error at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 has been removed from CMake.

  Update the VERSION argument <min> value.  Or, use the <min>...<max> syntax
  to tell CMake that the project requires at least <min> but has been updated
  to work with policies introduced by <max> or earlier.

  Or, add -DCMAKE_POLICY_VERSION_MINIMUM=3.5 to try configuring anyway.
```

- Add Flag here:- cmake -Dgtest_build_samples=OFF -Dgtest_build_tests=OFF -DCMAKE_POLICY_VERSION_MINIMUM=3.5 ../


```bash
g++ -std=c++17 test_TaskScheduler.cpp -lgtest -lgtest_main -pthread -o test_tasks
./test_tasks
```

## Code Style Checks

- brew install llvm
- echo 'export PATH="/opt/homebrew/opt/llvm/bin:$PATH"' >> ~/.zshrc
- source ~/.zshrc
- clang-tidy --version
- clang-tidy $(find . -name '*.cpp' ! -name 'test_*') -- -I/opt/homebrew/include

---

Unleash the Power of Clang Tide: Wash Away Code Smells with a Sparkle!

Say goodbye to the stench of messy code with Clang Tide, the ultimate code smell removal tool that leaves your software sparkling clean! 🚀 

Designed for developers who demand pristine, maintainable code, Clang Tide dives deep into your C++ codebase, sniffing out and scrubbing away those pesky code smells—like bloated functions, tangled classes, or sneaky duplicates—that slow down progress and stink up your project. 😷

With Clang Tide, you get:
Lightning-Fast Detection: Powered by Clang’s cutting-edge static analysis, it pinpoints code smells with surgical precision, saving you hours of manual debugging. 🕵️‍♂️

One-Tap Refactoring: Transform smelly code into clean, modular masterpieces with automated fixes that keep your project fresh and future-proof. 🧼

Linux-Friendly Freshness: Seamlessly integrates with gcc or clang on Linux, ensuring a smooth, hassle-free clean-up for every developer. 🐧

Scalable Shine: From small scripts to massive systems, Clang Tide tackles code smells of all sizes, boosting readability, maintainability, and team morale! ✨

Don’t let code smells linger and foul up your workflow. With Clang Tide, your codebase will smell as good as it runs—clean, crisp, and ready to impress! Try it now and experience the fresh difference! 🌊💻

For more details, check out clang.llvm.org or your favorite software development community!
