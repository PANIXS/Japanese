1. 查看hdfs文件系统根目录\
```hdfs dfs -ls /```
2. 在集群中一个机器上创建目录,其他机器也会同步创建\
```hdfs dfs -mkdir /test```
3. 将本地文件拷贝到hdfs中
    ```
    hdfs dfs -copyFromLocal  /data/testdata/mk.txt   /test
    hdfs dfs -cat  /test/mk.txt
    hdfs dfs -rm  /test/mk.txt
    ```

4. 将hdfs文件下载到本地文件系统\
    ```hdfs dfs -copyToLocal /test/mk.txt /data/testdata/mk2.txt```
5. 改变hdfs文件的权限\
```hdfs dfs -chmod 777 /test/mk.txt```
6. 打印块信息报告\
```hdfs fsck /output -blocks```
7. 