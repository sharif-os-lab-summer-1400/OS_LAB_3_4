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

- [ ] Write (in English or Persian) about each file in /proc/ directory:
    1. `[FILL HERE with description about meminfo]`
    1. `[FILL HERE with description about version]`
    1. `[FILL HERE with description about uptime]`
    1. `[FILL HERE with description about stat]`
    1. `[FILL HERE with description about mount]`
    1. `[FILL HERE with description about net directory (or file)]`
    1. `[FILL HERE with description about loadavg]`
    1. `[FILL HERE with description about interrupts]`
    1. `[FILL HERE with description about ioports]`
    1. `[FILL HERE with description about filesystem]`
    1. `[FILL HERE with description about cpuinfo]`
    1. `[FILL HERE with description about cmdline]`

- [ ] Place your source code for a program that shows details of processor:
    - [ ] `[FILL HERE with you source code]`

- [ ] Place your source code for a program that shows details of memory management sub-system:
    - [ ] `[FILL HERE with you source code]`

- [ ] Write your description about five important files at /proc/sys/kernel:
    - [ ] `[FILL HERE with you descript for 1st file]`
    - [ ] `[FILL HERE with you descript for 2nd file]`
    - [ ] `[FILL HERE with you descript for 3rd file]`
    - [ ] `[FILL HERE with you descript for 4th file]`
    - [ ] `[FILL HERE with you descript for 5th file]`

- [ ] Write your description about /proc/self file
    - [ ] `[FILL HERE with you description]`


## Source Code Submission

please submit all your codes in a zip file

 - [ ] `Zip File HERE`
