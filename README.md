 Run weblogic 10.3.6 with Docker
 
 #Download files from Oracle and get URL with transfer.sh
 #curl --upload-file ./wls1036_generic.jar https://transfer.sh/wls1036_generic.jar
 #curl --upload-file ./jdk-7u79-linux-x64.tar.gz.jar https://transfer.sh/jdk-7u79-linux-x64.tar.gz.jar

git clone https://github.com/acevedodamian/docker-weblogic1036.git

docker build -t myweblogic1036 --progress=plain --no-cache  \
--build-arg WLS_GENERIC_INSTALLER_URL=https://transfer.sh/O6i53F/wls1036_generic.jar  \
--build-arg JDK7_INSTALLER_URL=https://transfer.sh/MKmzl9/jdk-7u79-linux-x64.tar.gz  .

#Run docker image: 
docker run -d -ti -p 7001:7001 myweblogic1036

#http://localhost:7001/console/
#weblogic / weblogic01