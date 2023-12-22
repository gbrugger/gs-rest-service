Install Eclipse Temurin JDK

```
apt-get install -y wget apt-transport-https gnupg

wget -O - https://packages.adoptium.net/artifactory/api/gpg/key/public | sudo gpg --dearmour -o /usr/share/keyrings/adoptium.gpg

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/adoptium.gpg] https://packages.adoptium.net/artifactory/deb $(awk -F= '/^VERSION_CODENAME/{print$2}' /etc/os-release) main" | sudo tee /etc/apt/sources.list.d/adoptium.list

apt-get update

apt-get install temurin-21-jdk
```

Switch Java version

```
sudo update-alternatives --set java /usr/lib/jvm/temurin-21-jdk-amd64/bin/java
sudo update-alternatives --set javac /usr/lib/jvm/temurin-21-jdk-amd64/bin/javac
export JAVA_HOME=/usr/lib/jvm/temurin-21-jdk-amd64
```
