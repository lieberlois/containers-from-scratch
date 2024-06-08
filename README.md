# containers-from-scratch
Writing a container in a few lines of Go code, as seen at [DockerCon 2017](https://www.youtube.com/watch?v=MHv6cWjvQjM&t=1316s) and on [O'Reilly Safari](https://www.safaribooksonline.com/library/view/how-to-containerize/9781491982310/)

You need root permissions for this version to work. Or you can adapt it to be a rootless container by as shown in [these slides](https://speakerdeck.com/lizrice/rootless-containers-from-scratch). 

Note that the Go code uses some syscall definitions that are only available when building with GOOS=linux.


# Usage

Can be started using `go run main.go run /bin/bash`

Requires a Linux FS to be present at `/root/linux-fs`. This can be achieved using `docker pull ubuntu:latest && docker save ubuntu:latest > image.tar` and un-taring the image, and then the layer.tar tarball into the folder /root/linux-fs/
