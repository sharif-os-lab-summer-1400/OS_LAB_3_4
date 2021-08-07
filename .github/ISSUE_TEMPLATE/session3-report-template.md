---
name: فرم گزارش آزمایش سوم
about: برای نوشتن گزارش آزمایشگاه از این تمپلیت استفاده کنید
title: Session 3 Report
labels: documentation
assignees: fshahinfar1

---

Team Name: `97110285-97101286`

Student Name of member 1: `Mohammadreza Abdi`
Student No. of member 1: `97110285`

Student Name of member 2: `Alireza Ilami`
Student No. of member 2: `97101286`

NOTE: All of the cpp codes are submitted in a zip file at the end of the template. Although, I have put their screenshots for easier access.

- [x] Read Session Contents.

### Section 3.3.1
- [x] Investigate the /proc/ directory
    1. [x] ![image](https://user-images.githubusercontent.com/45389577/127737564-bdf72e45-7d14-496a-a002-23ee4577b47b.png)

### Section 3.3.2

- [ ] Do 5 subtasks from 1 to 5:
    1. [x] ![image](https://user-images.githubusercontent.com/45389577/127737698-699a0dcf-bb32-44f6-9123-28c5d26e0434.png)
        در اینجا ورژن هسته لینوکس، نام کاربری که آن را نصب کرده است، ورژن جی سی سی، نسخه دبینی که جی سی سی روی آن نصب شده است، و زمان کامپایل کرنل لینوکس را میتوان دید.
    2. [x] ![image](https://user-images.githubusercontent.com/45389577/127744249-8400d791-efdd-418b-86d7-5af625cc2a16.png)
            proc/partitions:    Partitioned devices are listed in dir: /dev/ . In proc/partitions we have their information such as major and minor number which are related to devicetype and identification number. And also their number of blocks.
            proc/uptime:    It shows two numbers. The first one is the total seconds that the machine is on since its last poweroff/reboot. The second number is the total time that all cores have spent the idle process. It can be greater than the first number with multiple cores.
    3. [x] `[FILL HERE with the program you write for this part (see experiment guide for information).]`
        ![image](https://user-images.githubusercontent.com/45389577/128593743-c862a7a1-0e47-454e-9a7a-defd4c55c3d2.png)
    5. [x] `[FILL HERE with screen capture from your programs execution.]`
        ![image](https://user-images.githubusercontent.com/45389577/128593809-023ca584-da46-49dc-a091-f3ec978fdcfe.png)
    7. [x] `Permission denied. We do not have the "Write" access for this file. Only root user can write on this file.`
        ![image](https://user-images.githubusercontent.com/45389577/128593884-b5db4dcd-90d6-492a-815b-75810ea4b58d.png)

## Section 3.3.3

- [x] Write (in English or Persian) about each file in /proc/(PID) directory:
    1. cmdline: if the process has parent and is not a zombie, this file contains the complete command line for the process.
    1. environ: when the process was started executing, the initial environment is set. all environment variables are listed in environ. the output is more clear with "strings" command. 
    1. stat: as its name, it shows the status information of the process. This file shows a lot of num,bers which they have a specific meaning by their order. for example one boolean number says whether this process is running or not. Or so others say if the file is a zombie or stopped or sleeping or etc.
    1. status: There are two files: sts and ststm. the status file is a combination of both, in a more human-readle language and format.
    1. statm: Shows the status of the process which is related to the memory usage. like shared pages, total memory usage, resident set size, etc.
    1. cwd: current working directory. similar to pwd. This is a symbolic link.
    1. exe: This file is a symbolic link to the actual pathname of the executed command. If you open it, it opens an executable file.
    1. root: We have a per-process root of the filesystem in linux kernel. this file references to the process's root directory. and works line the exe file.

- [x] Place your script for shwoing PID of running porcesses and their name here:
    - [x] ![image](https://user-images.githubusercontent.com/45389577/128609125-f7a812fd-b7a3-4758-a9cc-0e0d45a7150e.png)

- [x] Place your source code for a program that shows details of a program by receiving PID:
    - [x] ![image](https://user-images.githubusercontent.com/45389577/128608873-3c089e0f-137d-40fb-8d41-bffa3629773f.png)

### Section 3.3.4

- [x] Write (in English or Persian) about each file in /proc/ directory:
    1. meminfo: information about memory. such as total memory, cached mem, available mem, swap mem, etc.
    1. version: As mentioned in task 3.3.2.1
    1. uptime: As mentioned in task 3.3.2.2
    1. stat: CPU statistical info. how much time each cpu has spent on performing different works. the first line is the sum of all cpu blocks. when the system restarts, all these values start from 0 again.
    1. mounts: The 1st column specifies the device that is mounted. The 2nd column reveals the mount point. The 3rd column tells the file-system type. The 4th column tells you if it is mounted read-only (ro) or read-write (rw). The 5th and 6th columns are dummy values designed to match the format used in /etc/mtab.
    1. net: This shows various networking parameters and statisticse.g. /dev shows all network devices. /route shows kernet routing table, etc.
    1. loadavg: load average to both CPU and IO over time. The first three columns measure CPU and IO utilization of the last one, five, and 15 minute periods. The fourth column shows the number of currently running processes and the total number of processes. The last column displays the last process ID used. 
    1. interrupts: recording number of interrupts per IRQ. Showing the type of interrupt, device name, num of interrupts per CPU, etc.
    1. ioports: a list of currently registered port regions used for io communication with a device.
    1. filesystem: a special filesystem which lists all filesystems that arr currently supported by the kernel. It does not exist on a disk.
    1. cpuinfo: information about CPU. CPU type, Frequency, num of CPUs that are currently present, cpu cores, cache size, etc.
    1. cmdline: Containing commandline of the kernel. showing parameters passed to the kernel at the time it started.

- [x] Place your source code for a program that shows details of processor:
    - [x] ![image](https://user-images.githubusercontent.com/45389577/128610436-feed78b1-5a74-4355-a3e3-859ecdb72a55.png)`

- [x] Place your source code for a program that shows details of memory management sub-system:
    - [x] `[FILL HERE with you source code]`

- [x] Write your description about five important files at /proc/sys/kernel:
    - [x] dmesg_restrict: This toggle indicates whether unprivileged users are prevented from using dmesg(8) to view messages from the kernel’s log buffer. When dmesg_restrict is set to 0 there are no restrictions. When dmesg_restrict is set to 1, users must have CAP_SYSLOG to use dmesg(8).
    - [x] domainname: These files can be used to set the NIS/YP domainname of your box in exactly the same way as the command domainname.
    - [x] bootloader_type: This gives the bootloader type number as indicated by the bootloader, with a brief encoding for matching kernel header.
    - [x] ngouprs_max: Maximum number of supplementary groups, _i.e._ the maximum size which setgroups will accept.
    - [x] panic: The value in this file determines the behaviour of the kernel on a panic: if zero, the kernel will loop forever; if negative, the kernel will reboot immediately; if positive, the kernel will reboot after the corresponding number of seconds. When you use the software watchdog, the recommended setting is 60.
    - [x] pid_max: PID allocation wrap value. When the kernel’s next PID value reaches this value, it wraps back to a minimum PID value. PIDs of value pid_max or larger are not allocated.
    - [x] threads_max: This value controls the maximum number of threads that can be created using fork(). minimum is 1, maximum is given by the constant FUTEX_TID_MASK (0x3fffffff)
    
- [x] Write your description about /proc/self file
    - [x] /proc/self is a real symbolic link to the /proc/ subdirectory of the process that is making the call. It is not really a folder, it is a device driver (more accurately, a kernel module) exposing itself as a folder when someone wants to access it. Basically, /proc/self/ represents the process that's reading /proc/self/. So if you try to open /proc/self/ from a C program then it represents that program. If you try to do it from the shell then it is the shell etc.. 


## Source Code Submission

please submit all your codes in a zip file

 - [x] [OSLab3-Source_codes.zip](https://github.com/mohammadrezaabdi/OS_LAB_3_4/files/6949634/OSLab3-Source_codes.zip)

