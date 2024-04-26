# Exploring Archi

To build and modify the Archi and JArchi

To Pull new versions

```bash
git submodules update --remote
```

## Using Developer tutorial

* https://github.com/archimatetool/archi/wiki/Developer-Documentation

* Reproduction step https://github.com/eclipse-platform/eclipse.platform.swt/issues/1012

## Setup

Import `archi` into the git workfolder this will add a Eclipse `.metadata` to the git folders.
Import `plugins` into the git workfolder.                        

## Dependancies

### Java:

https://www.itzgeek.com/how-tos/linux/how-to-install-oracle-java-jdk-17-on-linux.html

https://adoptium.net/installation/linux/

* https://adoptium.net/en-GB/temurin/archive/?version=17
* https://github.com/adoptium/temurin17-binaries/releases/download/jdk-17.0.10%2B7/OpenJDK17U-jdk_x64_linux_hotspot_17.0.10_7.tar.gz


```bash
sudo -i
#Adoptium
apt install -y wget apt-transport-https gpg
wget -qO - https://packages.adoptium.net/artifactory/api/gpg/key/public | gpg --dearmor | tee /etc/apt/trusted.gpg.d/adoptium.gpg > /dev/null
echo "deb https://packages.adoptium.net/artifactory/deb $(awk -F= '/^VERSION_CODENAME/{print$2}' /etc/os-release) main" | tee /etc/apt/sources.list.d/adoptium.list
apt update # update if you haven't already
apt install temurin-17-jdk
```

### Maven

https://maven.apache.org/download.cgi
https://maven.apache.org/install.html

```bash
wget https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz

tar -xzvf apache-maven-3.9.6-bin.tar.gz -C ~/maven/

echo 'export PATH="~/maven/apache-maven-3.9.6/bin/:$PATH"' >> .profile
```

#### Other methods (Unused)

```bash
sudo apt update
sudo apt install -y libc6-x32 libc6-i386

curl -O OpenJDK17.deb https://download.oracle.com/java/17/latest/jdk-17_linux-x64_bin.deb

sudo dpkg -i jdk-17_linux-x64_bin.deb


curl -O OpenJDK17.tar.gz https://github.com/adoptium/temurin17-binaries/releases/download/jdk-17.0.10%2B7/OpenJDK17U-jdk_x64_linux_hotspot_17.0.10_7.tar.gz

tar -xzvf OpenJDK17.tar.gz /opt/
```


### Eclipse

* https://www.eclipse.org/downloads/packages/release/2023-12/r/eclipse-ide-rcp-and-rap-developers

### Build with Maven

```bash
mvn clean package -P product
```

# Plugins

https://github.com/archimatetool/archi/wiki/Developing-Import-and-Export-Plug-ins

Need to Edit `archi.product` and edit the `contents` tab to add the plugins to the Archi build.

To export the plugins:

Export the plug-in as a jar file from Eclipse (File -> Export -> Deployable plug-ins and fragments)

This will create a group of `.jar` files.

