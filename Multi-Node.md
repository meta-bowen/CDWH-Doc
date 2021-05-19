# 节点多挖文档

## 双挖节点地址
### MW
nodeA: http://198.44.168.213:7216
nodeB: http://43.250.174.32:7216
### SHARDER
nodeA: http://198.44.168.213:6216/
nodeB: http://43.250.174.32:6216/


## 双挖节点内存占用情况

### 0326
- 198.44.168.213:22运行双链内存占用情况：
    ```apache
    root@www:~/sharder# ps -ef|grep java
    root     30468     1  0 20:56 pts/6    00:00:49 /usr/lib/jvm/java-8-openjdk-amd64/bin/java -Xloggc:logs/gc.log -cp lib/*:conf -Dsharder.runtime.mode=noview -Dsharder.runtime.dirProvider=org.conch.env.DefaultDirProvider -jar cos.jar
    root     30638     1  0 20:57 pts/6    00:00:19 /usr/lib/jvm/java-8-openjdk-amd64/bin/java -Xloggc:logs/gc.log -cp lib/*:conf -Dsharder.runtime.mode=noview -Dsharder.runtime.dirProvider=org.conch.env.DefaultDirProvider -jar cos.jar
    root     31200 30137  0 23:51 pts/6    00:00:00 grep --color=auto java
    root@www:~/sharder# free -m
                  total        used        free      shared  buff/cache   available
    Mem:           3933        2316         739           4         877        1393
    Swap:             0           0           0
    ``` 
- 43.250.174.32运行双链的内存占用情况：
    ```
    root@www:~/mwfs# ps -ef|grep java
    root     16689     1  0 20:52 pts/3    00:00:55 /usr/lib/jvm/jdk8.0.181/bin/java -Xloggc:logs/gc.log -cp lib/*:conf -Dsharder.runtime.mode=noview -Dsharder.runtime.dirProvider=org.conch.env.DefaultDirProvider -jar cos.jar
    root     16768     1 32 20:53 pts/3    00:58:59 /usr/lib/jvm/jdk8.0.181/bin/java -Xloggc:logs/gc.log -cp lib/*:conf -Dsharder.runtime.mode=noview -Dsharder.runtime.dirProvider=org.conch.env.DefaultDirProvider -jar cos.jar
    root     17970 16648  0 23:57 pts/3    00:00:00 grep --color=auto java
    root@www:~/mwfs# free -m
                  total        used        free      shared  buff/cache   available
    Mem:           3933        3009         153           3         770         709
    Swap:             0           0           0
    
    ```

### 0325
43.250.175.32运行sharder、mw双链，内存占用情况：
```dotnetcli
root@www:~# free -m
              total        used        free      shared  buff/cache   available
Mem:           3933        2826         654           3         452         891
Swap:             0           0           0

```
