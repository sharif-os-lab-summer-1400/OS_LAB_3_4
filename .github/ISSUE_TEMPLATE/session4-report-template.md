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
    
    </div>

- [x] Program showing that memory of the parent and the child is seperate
    
    ```c
    #include <stdio.h>
    #include <sys/wait.h>
    #include <unistd.h>
    int main() {
        int ret = fork();
        int tmp = 0;
        if (ret == 0) {
            printf("tmp value 1 in child process: %d\n", tmp);
            tmp += 10;
            printf("tmp value 2 in child process: %d\n", tmp);
            return 23;
        } else {
            int rc = 0;
            wait(&rc);
            printf("tmp value 1 in parent process: %d\n", tmp);
            tmp += 10;
            printf("tmp value 2 in parent process: %d\n", tmp);
            printf("return code is %d\n", WEXITSTATUS(rc));
        }
        return 0;
    }
    ```
   <div dir="rtl">
   دقت کنید که در تابع بالا، مقدار تغییر یافته در متغیر
    tmp
     بعد از اجرای پردازه فرزند، در پردازه پدر قابل مشاهده نمی باشد، چرا پشته ی پردازه های پدر و فرزند مستقل از یک دیگر هستند.
   </div>

- [x] Program printing different messages for parent and child process
    
    ```c
    include <stdio.h>
    #include <sys/wait.h>
    #include <unistd.h>
    int main() {
        int ret = fork();
        if (ret == 0) {
            printf("I am the child.\n");
            return 23;
        } else {
            printf("I am the parent.\n");
            int rc = 0;
            wait(&rc);
            printf("return code is %d\n", WEXITSTATUS(rc));
        }
        return 0;
    }
    ```

- [ ] Program for the last task of this section
    1. [ ] `[FILL HERE with your source code]`
    1. [ ] `[FILL HERE with you description of the output`]

## Section 4.4.3

- [x] Program using `wait` and counting from 1 to 100
   
    ```c
    #include <stdio.h>
    #include <sys/wait.h>
    #include <unistd.h>
    #include <stdlib.h>
    int main() {
        int pid = fork();
        if (pid == 0) {
            for (int i=1; i<=100; i++)
                printf("%d\n", i);
            exit(0);
        } else {
            wait(NULL);
            printf("child execution is finished.\n");
        }
        return 0;
    }
    ```
    
   <div dir="rtl">
   پارامتر اول تابع
    wait
    یک پوینتر به یک متغیری از نوع 
    int
     است که بعد از پایان یافتن اجرای پردازه فرزند، مقداری را در آن متغیر قرار می دهد که می توان با استفاده از ماکروهایی مانند
    WIFEXITED
    یا 
    WIFSIGNALED
    نحوه خاتمه یافتن فرزند را متوجه شد و یا با استفاده از سایر ماکروهایی مانند
    WEXITSTATUS
    یا
    WSTOPSIG
    سایر اطلاعاتی را در ارتباط با مقدار برگردانده شده از فرزند یا تعداد سیگنال های توقف به آن را بدست آورد.
   </div>

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
