
## NAME : VASU VIGNESHWARAN P
## REG NO : 212224220119
# Linux-IPC-Shared-memory
Ex06-Linux IPC-Shared-memory

# AIM:
To Write a C program that illustrates two processes communicating using shared memory.

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - Shared Memory

### Step 3:

Execute the C Program for the desired output. 

# PROGRAM:
~~~
#include <stdio.h>
#include <sys/ipc.h>
#include <sys/shm.h>

int main()
{
        key_t key = ftok("shmfile", 65);
        int id = shmget(key, 1024, 0666 | IPC_CREAT);
        printf("Shared memory id = %d \n",id);
        char* str = (char*)shmat(shmid, (void*)0, 0);
        
        printf("Write Data : ");
        fgets(str, 1024, stdin);

        printf("Data written in memory: %s\n", str);
        shmdt(str);

        return 0;
}
~~~

## OUTPUT

![WhatsApp Image 2025-05-15 at 09 39 01_299469c6](https://github.com/user-attachments/assets/f11caae6-73fe-4346-8506-deb892c38eab)

# RESULT:
The program is executed successfully.
