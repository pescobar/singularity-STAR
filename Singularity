Bootstrap: docker
From: centos:7.3.1611

%runscript

   #"I can put here whatever I want to happen by default when the user runs the container"
   cat << EOF
STAR version 2.5.2b - https://github.com/alexdobin/STAR
This container provides binaries STAR and STARlong
To execute them do "singularity exec /path/to/container.img binary-name"
EOF

%post
 
   echo "Here we are installing software and other dependencies for the container!"
   yum -y install make gcc gcc-c++ zlib-devel
   cd /usr/local/src/
   curl -o STAR-2.5.2b.tar.gz  https://codeload.github.com/alexdobin/STAR/tar.gz/2.5.2b
   tar xf STAR-2.5.2b.tar.gz
   cd /usr/local/src/STAR-2.5.2b/source
   make STAR && make STARlong
   cp /usr/local/src/STAR-2.5.2b/source/{STAR,STARlong} /usr/local/bin

