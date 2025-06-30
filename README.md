# C_Threads_Mutexes 🧵🔒

![C_Threads_Mutexes](https://img.shields.io/badge/C_Threads_Mutexes-Active-brightgreen)

Welcome to the **C_Threads_Mutexes** repository! This collection of exercises was completed as part of the Operating Systems course during my Bachelor's Degree in Computer Science and Engineering at the University of Catania. Here, you will find various implementations and experiments with threads and mutexes in C, focusing on concurrent programming concepts.

## Table of Contents

- [Introduction](#introduction)
- [Topics Covered](#topics-covered)
- [Getting Started](#getting-started)
- [How to Use](#how-to-use)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Introduction

In today's software landscape, understanding concurrency is crucial. This repository aims to provide practical examples of using threads and mutexes in C. Each exercise focuses on different aspects of concurrent programming, allowing you to grasp fundamental concepts and apply them in real-world scenarios.

## Topics Covered

This repository includes exercises and examples on the following topics:

- Algorithms
- C Programming
- Concurrent Programming
- Data Structures
- Debugging Techniques
- English Language Documentation
- Git and GitHub Usage
- Imperative Programming
- Markdown Formatting
- Project Management Principles

## Getting Started

To get started, you can download the latest release from [here](https://github.com/Angelmmd/C_Threads_Mutexes/releases). Make sure to download the necessary files and execute them in your local development environment.

### Prerequisites

Before running the exercises, ensure you have the following installed:

- A C compiler (like GCC)
- Git for version control
- Basic understanding of C programming and concurrency concepts

## How to Use

1. **Clone the Repository**: Use the following command to clone the repository to your local machine:

   ```bash
   git clone https://github.com/Angelmmd/C_Threads_Mutexes.git
   ```

2. **Navigate to the Directory**:

   ```bash
   cd C_Threads_Mutexes
   ```

3. **Download and Execute**: Visit the [Releases section](https://github.com/Angelmmd/C_Threads_Mutexes/releases) to download the latest version. Follow the instructions in each exercise to run the code.

4. **Explore the Code**: Each exercise is well-documented. Read through the comments to understand the logic and flow of the program.

## Examples

Here are some examples of what you can expect in this repository:

### Example 1: Basic Thread Creation

This example demonstrates how to create and join threads in C.

```c
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>

void* threadFunction(void* arg) {
    printf("Hello from thread!\n");
    return NULL;
}

int main() {
    pthread_t thread;
    pthread_create(&thread, NULL, threadFunction, NULL);
    pthread_join(thread, NULL);
    return 0;
}
```

### Example 2: Using Mutexes

This example shows how to use mutexes to prevent data races.

```c
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>

pthread_mutex_t lock;

void* threadFunction(void* arg) {
    pthread_mutex_lock(&lock);
    // Critical section
    printf("Thread %d is in the critical section.\n", *(int*)arg);
    pthread_mutex_unlock(&lock);
    return NULL;
}

int main() {
    pthread_t threads[5];
    int threadArgs[5];

    pthread_mutex_init(&lock, NULL);

    for (int i = 0; i < 5; i++) {
        threadArgs[i] = i;
        pthread_create(&threads[i], NULL, threadFunction, &threadArgs[i]);
    }

    for (int i = 0; i < 5; i++) {
        pthread_join(threads[i], NULL);
    }

    pthread_mutex_destroy(&lock);
    return 0;
}
```

## Contributing

Contributions are welcome! If you have ideas for new exercises or improvements, feel free to fork the repository and submit a pull request. Please ensure your code adheres to the existing style and includes comments for clarity.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contact

For any questions or feedback, please reach out to me via GitHub or email. I appreciate your interest in my work and look forward to your contributions!

## Additional Resources

- [GNU C Library Documentation](https://www.gnu.org/software/libc/manual/)
- [POSIX Threads Programming](https://computing.llnl.gov/tutorials/pthreads/)
- [C Programming Language Book](https://en.wikipedia.org/wiki/The_C_Programming_Language)

Visit the [Releases section](https://github.com/Angelmmd/C_Threads_Mutexes/releases) for the latest updates and downloads. Thank you for checking out the **C_Threads_Mutexes** repository!