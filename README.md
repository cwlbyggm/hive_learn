"# hive_learn" 

<h3>1、配置 </h3><br>
环境变量

export HIVE_HOME=/home/hadoop/hive<br>
export PATH=$PATH:$HIVE_HOME/bin<br>
hive-site.xml 配置<br>
<!--
<property>
<name>javax.jdo.option.ConnectionURL</name>
<value>jdbc:mysql://weekend07:3306/hive?createDatabaseIfNotExist=true</value>
</property>
<property>
<name>javax.jdo.option.ConnectionDriverName</name>
<value>com.mysql.jdbc.Driver</value>
</property>
<property>
<name>javax.jdo.option.ConnectionUserName</name>
<value>root</value>
</property>
<property>
<name>javax.jdo.option.ConnectionPassword</name>
<value>123</value>
</property>
-->
元数据初始化<br>
schematool -initSchema -dbType mysql --verbose



<h3>2、hive 常用命令</h3><br>
1）hive  -f  hive.sql 批量执行sql<br>
2) hive# !PWD   当前路径<br>
3）load  data   local inpath '/opt/part.txt'  into table part_table partion(dt='20190411',dep='red');  装载数据<br>
3）load  data   local inpath '/opt/part.txt'  overwriteinto table part_table partion(dt='20190411',dep='red');  装载数据<br>
4) select * from tb  where dt='20190411'; 分区查询<br>
5） show partion tb ; 查看分区<br>
6）   create  table hive_2019   建表<br>
 (  name  string ,<br>
    salary  float,<br><br>
    gender string,<br>
    level string   <br>
    )<br>
    patitrioned by (dt string,dev string)<br>
    row format delimited fields terminated by ','<br>
    stored as  textfile;  存储不压缩，另外的格式压缩<br>

6) alter table tb drop partion (dt='',dev='') 删除分区<br>
7) alter table tb rename to tb_new  表重命名 <br>
8) alter table tb  change a a1;  修改字段<br>



<h3>3、sql 注意事项</h3><br>
1）分区字段不能出现在建表字段，分区sql 接在建表sql后面<br>
