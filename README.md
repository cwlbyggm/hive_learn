"# hive_learn" 

<h3>1、配置 </h3><br>
环境变量

export HIVE_HOME=/home/hadoop/hive
export PATH=$PATH:$HIVE_HOME/bin
hive-site.xml 配置
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

元数据初始
schematool -initSchema -dbType mysql --verbose



<h3>2、hive 常用命令</h3><br>
1）hive  -f  hive.sql 批量执行sql<br>
2) hive# !PWD   当前路径
3）
