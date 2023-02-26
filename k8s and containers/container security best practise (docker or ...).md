#container #docker 

![[Pasted image 20230221010350.png]]


keep docker host and container runtime updated ( EXP: by using an os like coreOs [1][1] )
docker runtime in non root
container should run in non privileged mode


don't put hard written secret in

docker read only filesystem and volume

EXP of minimalist image:
google distroless





https://benlobaugh.medium.com/how-to-secure-docker-containers-with-a-read-only-filesystem-b27230f6efb

[1]: https://major.io/p/docker-compose-on-coreos/
[2]: https://sysdig.com/blog/dockerfile-best-practices/
[3]: https://www.tigera.io/learn/guides/container-security-best-practices/docker-security/
[4]: https://github.com/dnaprawa/dockerfile-best-practices
[5]: https://devopswithdocker.com/part-3/3-using-non-root-user
[6]: https://matt-rickard.com/docker-without-docker