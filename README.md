# hadoop-problems
Some problems encountered when I started hadoop.


1、If the system is 64-bit, you cannot start hdfs: ./sbin/start-dfs.sh. And have the following errors:


sed: -e expression #1, char 6: unknown option to `s'  
HotSpot(TM): ssh: Could not resolve hostname HotSpot(TM): Name or service not known  
64-Bit: ssh: Could not resolve hostname 64-Bit: Name or service not known  
Java: ssh: Could not resolve hostname Java: Name or service not known  
Server: ssh: Could not resolve hostname Server: Name or service not known  
VM: ssh: Could not resolve hostname VM: Name or service not known  


Solution：


vi etc/hadoop/hadoop-env.sh  


add：

exportHADOOP_COMMON_LIB_NATIVE_DIR=${HADOOP_PREFIX}/lib/native    

modify：

export HADOOP_OPTS="-Djava.library.path=$HADOOP_PREFIX/lib" 
