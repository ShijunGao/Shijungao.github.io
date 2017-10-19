*本地新建及初始化*
``` bash
$ mkdir learngit
$ cd learngit
$ git init

```

*关联GitHub*
``` bash
$ git remote add [Your GitHub Repertories]

```
*提交推送*
``` bash
$ git add .
$ git commit -m "what's change"
$ git push orgin branch
```
*创建分支*
``` bash
$ git checkout orphan gh-pages
```
*切换分支*
``` bash
git checkout master
```
*查看bash*
``` bash
$ cat ~/.bash_history
```
*正则匹配文件*
``` bash
$ grep 'Gary' /etc/passwd
```
*匹配目录*
``` bash
$ grep -r 'Gary' /var/log
```
*管道*
``` bash
$ cat /etc/passwd | grep 'Gary'
$ ls /etc | grep 'ssh'
```
*重定向*
``` bash
$ echo 'Hello World' > ~/test.txt  
```
*ping*
``` bash
$ ping StudyInDUT.com             //Ctrl + C
$ ping -c 4 StudyInDUT.com
```
*netstat*
``` bash
$ netstat -lt
$ netstat -tulpn
```
*ps*
``` bash
$ ps -aux                       //当前进程
```
