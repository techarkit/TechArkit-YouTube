# Build container

```buildah from centos
buildah images
buildah containers
curl -sSL https://ftp.gnu.org/gnu/hello/hello-2.10.tar.gz -o hello-2.10.tar.gz
buildah copy centos-working-container hello-2.10.tar.gz /tmp/ 
buildah run centos-working-container yum install -y tar gcc make 
buildah run centos-working-container yum clean all
buildah run centos-working-container tar xvzf /tmp/hello-2.10.tar.gz -C /opt
buildah config --workingdir /opt/hello-2.10 centos-working-container
buildah run centos-working-container ./configure
buildah run centos-working-container make
buildah run centos-working-container make install
buildah run centos-working-container hello –v
buildah config --entrypoint /usr/local/bin/hello centos-working-container
buildah commit --format docker centos-working-container firstbuildah:latest
buildah images
podman save -o mybuild1.tar localhost/hello2latest
podman rmi 638d3f915ea2 –f
podman load -i mybuild1.tar```

# Building container image from scratch
buildah from scratch
container1=$(buildah mount working-container)
yum install --installroot $container1 bash coreutils --releasever 8 --setopt install_weak_deps=false
yum clean all --installroot $container1
buildah config --cmd /bin/bash working-container
buildah config --label name=baseimage working-container
buildah umount working-container
buildah commit working-container baseimage
buildah images
podman inspect localhost/baseimage
podman run --rm -it localhost/baseimage /bin/bash


## Clean up ##
buildah rm working-container
buildah rmi working-container
