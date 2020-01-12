# Linux System Essentials from Data Analyst Perspective

* Login as Sudo/ Root user
```bash
sudo su -
```
* update the apt package index
```bash
sudo apt-get update
```
* Upgrade all the packages intalled to the newest version if available
```bash
sudo apt-get upgrade -y
```

* First, update the apt package index with:
```bash
sudo apt update
```

* Htop, Package to view the linux server processes
```bash
apt-get install htop
```

## Java
---
Before installing Oracle Java make sure you read the [Oracle JDK License](https://www.oracle.com/technetwork/java/javase/terms/license/javase-license.html "Oracle JDK Lisence in this link"). The license permits only non-commercial use of the software, such as personal use and development use.

---
* Install the default Java OpenJDK package</br>

_this will install the defult java version which will be Java 11_
```bash
sudo apt install default-jdk
```
* Check the version using
```bash
java -version
```
* To install the Java version 8
```bash
sudo apt install openjdk-8-jdk
```
### ***To set the Default version of JAVA***
---
```bash
sudo update-alternatives --config java
```
```bash
Output:
There are 3 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                            Priority   Status
------------------------------------------------------------
* 0            /usr/lib/jvm/java-11-openjdk-amd64/bin/java      1111      auto mode
  1            /usr/lib/jvm/java-11-openjdk-amd64/bin/java      1111      manual mode
  2            /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java   1081      manual mode

Press <enter> to keep the current choice[*], or type selection number:
```

*To change the default Java version just enter the version number (the number in the Selection column) and press Enter*

### ***Set Java home environment variable***
---
Some applications written in Java are using the JAVA_HOME environment variable to determine the Java installation location.

**To set the JAVA_HOME environment variable, first, you need to find out the Java installation paths using the update-alternatives command*
```bash
sudo update-alternatives --config java
```
In our case, the installation paths are as follows:
OpenJDK 8 is located at `/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java`

Copy the installation path of your preferred installation. Next, open the `/etc/environment` file:

```bash
sudo nano /etc/environment
```
*Add the following line at the end of the line*
```bash
JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64"
```
***Make sure you replace the path with the path to your preferred Java version.***

You can either log out and log in or run the following source command to apply the changes to your current session:
```bash
source /etc/environment
```

to verify the `JAVA_HOME` Env Variable is set correct :
```bash
echo $JAVA_HOME
```
### ***Uninstall Java Version***
---

If for any reason you want to uninstall the Java package, you can uninstall it like any other package installed with apt.

For example, if you want to uninstall the openjdk-8-jdk package run:
```bash
sudo apt remove openjdk-8-jdk
```




