# [Koffer](https://github.com/containercraft/Koffer) Collector Plugin | OSP Infrastructure Artifacts
This automation provides a unified and standardized tarball of OSP artifacts to
augment restricted or airgap infrastructure deployment.

Features:
  - CloudCtl compatible
  - Low side SHA256 artifact bundle metadata (for high side bit integrity validation)
  - Low side injestion direct to "pre-hydrated" registry stateful path
  - Idempotent, can be used to additively upload artifacts to pre-existing collection

Artifacts:
  - OpenStack [Container Images]
    
## Usage: Execute Collector Plugin with Koffer Engine
```
 mkdir -p ${HOME}/bundle && \
 podman run -it --rm --pull always \
     --volume ${HOME}/bundle:/root/bundle:z \
     --volume ${HOME}/.docker/config.json:/root/.docker/config.json:z \
   docker.io/cloudctl/koffer:latest bundle --silent \
     --plugin collector-ocp
```
[Container Images]:https://registry.redhat.io/v1/search?q=%27rhosp-rhel8%20or%20rhceph-4%20or%20ose-grafana%20or%20ose-prometheus%27
