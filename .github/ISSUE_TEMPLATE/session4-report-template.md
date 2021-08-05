---
name: فرم گزارش آزمایش چهارم
about: برای نوشتن گزارش آزمایشگاه از این تمپلیت استفاده کنید
title: Session 4 Report
labels: documentation
assignees: fshahinfar1

---

Team Name: `97110285-97101286`

Student Name of member 1: `Mohammadreza Abdi`
Student No. of member 1: `97110285`

Student Name of member 2: `Alireza Ilami`
Student No. of member 2: `97101286`

- [x] Read Session Contents.

### Section 4.4.1
- [x] Investigate the ps command
    
    ![image](https://user-images.githubusercontent.com/45341111/128358902-9bf2cbe6-f853-4459-a79d-8af64f3a97a0.png)
    
- [x] Infromation about processes with PID = 1
    
<div dir="rtl">
    
    پردازه systemd یا init، اولین پردازه ساخته شده در لینوکس می باشد
    این پردازه به طور کلی وظیفه مدیریت سیستم و سرویس های آن را بر عهده دارد.
    هدف اصلی این پردازه، پیکربندی کردن سرویس های هسته لینوکس در بین توزیع های مختلف است.
    همچنین این پردازه سرویس هایی برای راه اندازی و مدیریت فضای کاربر در هنگام بوت شدن سیستم شروع می کند.  
    
    هنگام بوت شدن سیستم عامل، مولفه های این پردازه از چندین فایل متنی ساخته می شود
     (/etc/systemd/system به عنوان مثال در مسیر) 
    سپس این پردازه شروع به بالا آوردن سرویس ها و پردازه های دیگر می کند
</div>

- [x] Program using getpid

```c 
#include <stdio.h>
#include <unistd.h>

int main(){
   printf("current process id: %d\n", getpid());
   return 0;
}
```

### Section 4.4.2


- [x] Program using getppid

    ```c 
    #include <stdio.h>
    #include <unistd.h>

    int main(){
       printf("current process id: %d\n", getpid());
       return 0;
    }
    ```
    <div dir="rtl">
   
   پردازه پدر
   bash
   می باشد.
   این پردازه همان ترمینال می باشد و دستوراتی را که کاربر در آن وارد می کند، اجرا می کند.
   از آن جایی که دستوری کامپایل و اجرای کد در
   bash 
   اجرا شده، بنابراین پردازه پدر همان 
   bash
   خواهد بود.     
   
    </div>
    
   ![image](https://user-images.githubusercontent.com/45341111/128375348-d30122e8-f6ee-425a-bc99-fc3a3492faec.png)

- [x] Describe the C program (fork program)
    <div dir="rtl">
    
    در این کد، ابتدا از پردازه اصلی برنامه یک پردازه فرزند ساخته می شود.
    پردازه پدر منتظر پردازه فرزند می ماند تا آن اتمام یابد.
     پردازه فرزند مقدار 23 را برمی گرداند. سپس پردازه پدر این مقدار را دریافت می کند و در خروجی چاپ می کند.
    دقت کنید که بعد از تابع
    fork
    مقدار
    ret
    برای پردازه پدر برابر با
    pid
    فرزند و برای پردازه فرزند برابر با 0 می باشد.
    لذا پردازه اول کد داخل 
    if
    را اجرا می کند و پردازه پدر کد داخل
    else
    را.
    
    </div

- [ ] Program showing that memory of the parent and the child is seperate
    1. [ ] `[FILL HERE with your source code]`

- [ ] Program printing different messages for parent and child process
    1. [ ] `[FILL HERE with your source code]`

- [ ] Program for the last task of this section
    1. [ ] `[FILL HERE with your source code]`
    1. [ ] `[FILL HERE with you description of the output`]

## Section 4.4.3

- [ ] Program using `wait` and counting from 1 to 100
    1. [ ] `[FILL HERE with your source code]`
    1. [ ] `[FILL HERE about description for the parameter of wait system call]`

- [ ] Program showing process adoption
    1. [ ] `[FILL HERE with your source code]`
    1. [ ] `[FILL HERE an image from execution of your program]`

### Section 4.4.4

- [ ] Describe following commands/APIs:
    1. `[FILL HERE with description about execv]`
    1. `[FILL HERE with description about execl]`
    1. `[FILL HERE with description about execvp]`
    1. `[FILL HERE with description about execlp]`

- [ ] Program which forks and executues `ls` command
    1. [ ] `[FILL HERE with your source code]`
    1. [ ] `[FILL HERE an image from execution of your program]`

## Source Code Submission

please submit all your codes in a zip file

 - [ ] `Zip File HERE`
