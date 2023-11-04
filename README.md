# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

## AIM:
To Implement the Inter Process Communication using pipe

## ALGORITHM:
### step 1.Create a child process usingfork().

### step 2.Create a simple pipe with C, we make use of the pipe() systemcall.

### step 3.Create two file descriptor fd[0] is set up for reading, fd[1] isset up forwriting.

### step 4.Close the read end of parent process using close() and perform writeoperation.

### step 5.Close the write end of child process and performreading.

### step 6.Display thetext.

## PROGRAM:
```
#include <stdio.h>
int main()
{
int fd[2],child; char a[10];
printf("\nEnter the string : ");
scanf("%s",a);
pipe(fd);
child=fork();
if(!child)
{
close(fd[0]);
write(fd[1],a,5); wait(0);
}
else
{
close(fd[1]);
read(fd[0],a,5); printf("The string received from pipe is : %s",a);
}
return 0;
}
```
## OUTPUT:
![image](https://github.com/Afsarjumail/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/118343395/7c37b4e9-699b-4064-9eed-c23ef46d831d)

## RESULT:
Thus the IPC using pipes mechanisms is illustrated using c program successfully


