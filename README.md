git clone https://github.com/acevedodamian/docker-weblogic1036.git

 #Bajar archivos y generar URL con transfer.sh
 #curl --upload-file ./wls1036_generic.jar https://transfer.sh/wls1036_generic.jar

docker build  \
--build-arg WLS_GENERIC_INSTALLER_URL=https://transfer.sh/O6i53F/wls1036_generic.jar  \
--build-arg JDK7_INSTALLER_URL=https://transfer.sh/MKmzl9/jdk-7u79-linux-x64.tar.gz  \
.

 #Run docker image: 

docker run -d -ti -p 7001:7001 myweblogic1036