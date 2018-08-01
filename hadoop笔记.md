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
7. hdfs系统默认存储在临时文件夹下面,linux每次重启时都会删除,因此必须要配置core-site.xml中的
hadoop.tmp.dir属性,如:
    ```
    <property>
            <name>hadoop.tmp.dir</name>
            <value>file:/data/hdfs/tmp</value>
            <description>A base for other temporary directories.</description>
    </property>

    ```
 8. hadoop shell的使用:
 hdfs dfs 和 hadoop fs 是一样的
 9. 当在hdfs中设置了副本数后,通过hdfs shell传上去的会采用这个参数,而java api上传的文件则不会,除非设置一下,否则会采用hadoop默认的3