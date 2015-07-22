Java SE Development Kit 8
=========================

--------------------------------------------------

## Link

官方站点:

<http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html>

安装教程:

<https://www.digitalocean.com/community/tutorials/how-to-install-java-on-centos-and-fedora>

## 安装

**rpm package install**
	
	# wget http://192.168.31.121/install/Linux/jdk-8u51-linux-x64.rpm
	# rpm -vih jdk-8u51-linux-x64.rpm
    # java -version

**gz unzip install**  
  
     # wget http://192.168.31.121/install/Linux/jdk-8u45-linux-x64.gz
     # tar xvf jdk-8u45-linux-x64.gz 
     # mv jdk1.8.0_45 /opt/ 
     # sudo chown -R root: /opt/jdk1.8.0_45 
     # sudo alternatives --install /usr/bin/java java /opt/jdk1.8.0_45/bin/java 1 
     # sudo alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_45/bin/javac 1 
     # sudo alternatives --install /usr/bin/jar jar /opt/jdk1.8.0_45/bin/jar 1 
     # java -version 	
     
-------------------------
*Cassandra 2015-07-17*     