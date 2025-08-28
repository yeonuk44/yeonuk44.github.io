---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_C_Context
title: About C Context
# title: About C Context
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2025-08-20 09:00:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

## **C Context: This article examines the core concepts** of processes and threads.

Hello!

In software development, **Context** refers to the state and environment while the program is running.

In particular, in C language and operating system-level programming, context acts as an important factor when **Process** and **Thread** are executed.

In this article, we will look at the definition and role of context from a C programming perspective, and how to manage it.

{:data-align="center"}

<!-- outline-end -->

### **What is the context?**?

Context is simply **a collection of information needed to run a program.**.

1. **Register status**: Values stored in the CPU register (e.g., program counter, stack pointer, etc.).
2. **Memory Status**: Heaps, stacks, data sections, etc. used by the process.
3. **I/O status**: file descriptors, network connections, etc.
4. **Scheduling information**: information that determines when the operating system runs the process.

### **Type of context**

1. **Process context**

   - The operating system maintains the **process context** when a single program runs.
   - This includes memory mapping, file descriptors, scheduling information, and so on.
   - For example, a 'fork()' system call copies the context of the parent process to the child process.

2. **Thread Context**
   - Threads run independently within the process, and the **thread context** manages the status for those threads.
   - Register values and stack information are the main parts.
   - Threads share the same process context, but stacks and registers are unique.

### **Context Switching**

**Context switching** occurs when the CPU switches from one process (or thread) to another.

The operating system stores the context of the previous process and restores the context of the next process.

#### **Stages of context switching**

1. Save the context of the currently running process.
2. Load the context of the next process to run.
3. The CPU runs the following process.

#### **Cost of context switching**

- Save and restore operations result in overhead.
- In particular, cache miss and memory access can cause performance degradation.

### **Manage context in C language**

Because language C can directly control hardware and memory, contextual management plays an important role.  
Typically, the following elements are used for context management:

#### **1. `setjmp`와 `longjmp`**

- **`setjmp`**: Saves the current context.
- **`longjmp'**: Restore to saved context.

```c
#include <setjmp.h>
#include <stdio.h>

jmp_buf buffer;

void second() {
    printf("Second function\n");
    longjmp(buffer, 1); // 저장된 위치로 복원
}

void first() {
    if (setjmp(buffer) == 0) {
        printf("First function\n");
        second();
    } else {
        printf("Back to first function\n");
    }
}

int main() {
    first();
    return 0;
}
```

#### **2. POSIX Threads**

- Pthreads is a library for implementing multi-threading in C, which supports thread context management.

```c
#include <pthread.h>
#include <stdio.h>

void* thread_function(void* arg) {
    printf("Thread ID: %lu\n", pthread_self());
    return NULL;
}

int main() {
    pthread_t thread;
    pthread_create(&thread, NULL, thread_function, NULL);
    pthread_join(thread, NULL);
    return 0;
}
```

### **The importance of context management**

Context management is key to efficient program execution.

1. **Stability**  
   Even if an unexpected situation (for example, an interrupt) occurs while the program is running, it can be recovered normally.

2. **Multi-tasking**  
   Optimizes CPU resources by efficiently managing multiple processes and threads.

3. **Debugging and error recovery**  
   You can save and handle the status of the program in exceptional situations.

### **Conclusion**

C context refers to the environment and state in which processes and threads run, and effectively managing them can increase stability and performance in multitasking environments.

In particular, tools such as 'setjmp', 'longjmp', and Pthreads are useful when dealing with contexts in the C language.

Understanding the context allows you to design better system programs and multithreaded applications.

**Remember the importance of context management and try to write efficient code!** 🚀
