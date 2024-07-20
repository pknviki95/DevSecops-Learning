# Docker

#### Official Documentation link : [Official Documentation link](https://docs.docker.com/guides/)

#### docker version:

- ```docker version``` returns the version of docker installed in your PC(client) and docker engine running in background(docker deamon).
- If it throws error then it is not installed properly or docker service is not running in your PC.

```sh
pknviki95@ubuntu18:~/pknviki/study/DevSecops-Learning/Docker$ docker version
```
#### output:
```sh
Client: Docker Engine - Community
Cloud integration: v1.0.35+desktop.13
Version:           23.0.1
API version:       1.42
Go version:        go1.19.5
Git commit:        a5ee5b1
Built:             Thu Feb  9 19:46:49 2023
OS/Arch:           linux/amd64
Context:           default

Server: Docker Engine - Community
Engine:
Version:          23.0.1
API version:      1.42 (minimum version 1.12)
Go version:       go1.19.5
Git commit:       bc3805a
Built:            Thu Feb  9 19:46:49 2023
OS/Arch:          linux/amd64
Experimental:     true
containerd:
Version:          1.6.18
GitCommit:        2456e983eb9e37e47538f59ea18f2043c9a73640
runc:
Version:          1.1.4
GitCommit:        v1.1.4-0-g5fd4c4d
docker-init:
Version:          0.19.0
GitCommit:        de40ad0
```
#### docker info:


- ```docker info``` returns most configuration values of the docker engine.
- Info such as version of various ```docker features,containers,Images```  etc,

```sh
pknviki95@ubuntu18:~/pknviki/study/DevSecops-Learning/Docker$ docker info
```
#### output:
```sh
Client:
Context:    default
Debug Mode: false
Plugins:
buildx: Docker Buildx (Docker Inc.)
    Version:  v0.14.0-desktop.1
    Path:     /usr/lib/docker/cli-plugins/docker-buildx
compose: Docker Compose (Docker Inc.)
    Version:  v2.27.0-desktop.2
    Path:     /usr/lib/docker/cli-plugins/docker-compose
debug: Get a shell into any image or container (Docker Inc.)
    Version:  0.0.29
    Path:     /usr/lib/docker/cli-plugins/docker-debug
dev: Docker Dev Environments (Docker Inc.)
    Version:  v0.1.2
    Path:     /usr/lib/docker/cli-plugins/docker-dev
extension: Manages Docker extensions (Docker Inc.)
    Version:  v0.2.23
    Path:     /usr/lib/docker/cli-plugins/docker-extension
feedback: Provide feedback, right in your terminal! (Docker Inc.)
    Version:  v1.0.4
    Path:     /usr/lib/docker/cli-plugins/docker-feedback
init: Creates Docker-related starter files for your project (Docker Inc.)
    Version:  v1.1.0
    Path:     /usr/lib/docker/cli-plugins/docker-init
sbom: View the packaged-based Software Bill Of Materials (SBOM) for an image (Anchore Inc.)
    Version:  0.6.0
    Path:     /usr/lib/docker/cli-plugins/docker-sbom
scan: Docker Scan (Docker Inc.)
    Version:  v0.23.0
    Path:     /usr/libexec/docker/cli-plugins/docker-scan
scout: Docker Scout (Docker Inc.)
    Version:  v1.8.0
    Path:     /usr/lib/docker/cli-plugins/docker-scout

Server:
Containers: 10
Running: 0
Paused: 0
Stopped: 10
Images: 2
Server Version: 23.0.1
Storage Driver: overlay2
Backing Filesystem: extfs
Supports d_type: true
Using metacopy: false
Native Overlay Diff: true
userxattr: false
Logging Driver: json-file
Cgroup Driver: cgroupfs
Cgroup Version: 1
Plugins:
Volume: local
Network: bridge host ipvlan macvlan null overlay
Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
Swarm: inactive
Runtimes: io.containerd.runc.v2 runc
Default Runtime: runc
Init Binary: docker-init
containerd version: 2456e983eb9e37e47538f59ea18f2043c9a73640
runc version: v1.1.4-0-g5fd4c4d
init version: de40ad0
Security Options:
apparmor
seccomp
Profile: builtin
Kernel Version: 5.4.0-150-generic
Operating System: Ubuntu 18.04.6 LTS
OSType: linux
Architecture: x86_64
CPUs: 8
Total Memory: 7.681GiB
Name: ubuntu18
ID: WR5E:AZWA:JRP7:AWAS:66KV:BLXH:FWRC:E74H:MGUR:DP4W:UT24:IY77
Docker Root Dir: /var/lib/docker
Debug Mode: false
Username: pknviki95
Registry: https://index.docker.io/v1/
Experimental: true
Insecure Registries:
127.0.0.0/8
Live Restore Enabled: false

WARNING: API is accessible on http://0.0.0.0:4243 without encryption.
        Access to the remote API is equivalent to root access on the host. Refer
        to the 'Docker daemon attack surface' section in the documentation for
        more information: https://docs.docker.com/go/attack-surface/
WARNING: No swap limit support
```

#### docker:


- It return the various commands related to docker.
- commands are distinguished based on usage common,management,swarm.
- There are new syntax created on docker with management commands for efficiency
    
    ```docker [command] <option>```
    
    ```docker [management command] [sub command] <option>```


```sh
pknviki95@ubuntu18:~/pknviki/study/DevSecops-Learning/Docker$ docker
```
#### output:
```sh
Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Common Commands:
run         Create and run a new container from an image
exec        Execute a command in a running container
ps          List containers
build       Build an image from a Dockerfile
pull        Download an image from a registry
push        Upload an image to a registry
images      List images
login       Log in to a registry
logout      Log out from a registry
search      Search Docker Hub for images
version     Show the Docker version information
info        Display system-wide information

Management Commands:
builder     Manage builds
buildx*     Docker Buildx (Docker Inc., v0.14.0-desktop.1)
checkpoint  Manage checkpoints
compose*    Docker Compose (Docker Inc., v2.27.0-desktop.2)
container   Manage containers
context     Manage contexts
debug*      Get a shell into any image or container (Docker Inc., 0.0.29)
dev*        Docker Dev Environments (Docker Inc., v0.1.2)
extension*  Manages Docker extensions (Docker Inc., v0.2.23)
feedback*   Provide feedback, right in your terminal! (Docker Inc., v1.0.4)
image       Manage images
init*       Creates Docker-related starter files for your project (Docker Inc., v1.1.0)
manifest    Manage Docker image manifests and manifest lists
network     Manage networks
plugin      Manage plugins
sbom*       View the packaged-based Software Bill Of Materials (SBOM) for an image (Anchore Inc., 0.6.0)
scan*       Docker Scan (Docker Inc., v0.23.0)
scout*      Docker Scout (Docker Inc., v1.8.0)
system      Manage Docker
trust       Manage trust on Docker images
volume      Manage volumes

Swarm Commands:
swarm       Manage Swarm

Commands:
attach      Attach local standard input, output, and error streams to a running container
commit      Create a new image from a container's changes
cp          Copy files/folders between a container and the local filesystem
create      Create a new container
diff        Inspect changes to files or directories on a container's filesystem
events      Get real time events from the server
export      Export a container's filesystem as a tar archive
history     Show the history of an image
import      Import the contents from a tarball to create a filesystem image
inspect     Return low-level information on Docker objects
kill        Kill one or more running containers
load        Load an image from a tar archive or STDIN
logs        Fetch the logs of a container
pause       Pause all processes within one or more containers
port        List port mappings or a specific mapping for the container
rename      Rename a container
restart     Restart one or more containers
rm          Remove one or more containers
rmi         Remove one or more images
save        Save one or more images to a tar archive (streamed to STDOUT by default)
start       Start one or more stopped containers
stats       Display a live stream of container(s) resource usage statistics
stop        Stop one or more running containers
tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
top         Display the running processes of a container
unpause     Unpause all processes within one or more containers
update      Update configuration of one or more containers
wait        Block until one or more containers stop, then print their exit codes

Global Options:
    --config string      Location of client config files (default "/home/pknviki95/.docker")
-c, --context string     Name of the context to use to connect to the daemon (overrides DOCKER_HOST env var and default context set with "docker context use")
-D, --debug              Enable debug mode
-H, --host list          Daemon socket(s) to connect to
-l, --log-level string   Set the logging level ("debug", "info", "warn", "error", "fatal") (default "info")
    --tls                Use TLS; implied by --tlsverify
    --tlscacert string   Trust certs signed only by this CA (default "/home/pknviki95/.docker/ca.pem")
    --tlscert string     Path to TLS certificate file (default "/home/pknviki95/.docker/cert.pem")
    --tlskey string      Path to TLS key file (default "/home/pknviki95/.docker/key.pem")
    --tlsverify          Use TLS and verify the remote
-v, --version            Print version information and quit

Run 'docker COMMAND --help' for more information on a command.

For more help on how to use Docker, head to https://docs.docker.com/go/guides/
```
