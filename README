Linux kernel - XCG
============
XCG: Decoupling Control from Configuration to Improve the Scalability of Cgroup

### How to use the extend cgroup (XCG)
Write an ioctl program and run it:
```c
#include <stdio.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>
#include <sys/ioctl.h>
#include <unistd.h>

#define CGRP_MAGIC 'x'
#define CGRP_RSBUF _IO(CGRP_MAGIC, 0)
#define CGRP_TAG _IO(CGRP_MAGIC, 1)
#define CGRP_FILES _IO(CGRP_MAGIC, 2)

int main(void) {
    int fd;


    fd = open("/sys/fs/cgroup/", O_RDONLY | O_DIRECTORY);
    if(fd < 0) {
        perror("open");
        return -1;
    }
    ioctl(fd, CGRP_TAG, 1);


    close(fd);
    return 0;
}
```
This program uses the iotcl command to enable xcg. Subsequent new cgroups under /sys/fs/cgroup will be created through XCG.

### run bucketbench tests
```shell
git clone https://github.com/estesp/bucketbench.git
cd bucketbench && sudo ./bucketbench --log-level=debug run -b examples/basic.yaml
```

Linux kernel
============
There are several guides for kernel developers and users. These guides can
be rendered in a number of formats, like HTML and PDF. Please read
Documentation/admin-guide/README.rst first.

In order to build the documentation, use ``make htmldocs`` or
``make pdfdocs``.  The formatted documentation can also be read online at:

    https://www.kernel.org/doc/html/latest/

There are various text files in the Documentation/ subdirectory,
several of them using the reStructuredText markup notation.

Please read the Documentation/process/changes.rst file, as it contains the
requirements for building and running the kernel, and information about
the problems which may result by upgrading your kernel.

