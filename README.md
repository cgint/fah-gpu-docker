## Related links

- [Official Docker Hub fah-gpu](https://hub.docker.com/r/foldingathome/fah-gpu)
- [Troubleshooting](https://foldingathome.org/support/faq/troubleshooting/)
- [Docker Hub Image - cgint/fah-gpu-cuda-11.7.1-base-ubuntu22.04](https://hub.docker.com/repository/docker/cgint/fah-gpu-cuda-11.7.1-base-ubuntu22.04/general)
- [My 'worldgint' Donor Statistics](https://stats.foldingathome.org/donor/id/677134766)

# Why this repo ?
I wanted to have a dockerized version of Folding At Home that I can easily setup again on a machine using NVIDIA-GPU.

As I found a fix from https://github.com/sanori I wanted to make the work i invested available to people and ideally also help others to make use of a complete Docker-Setup for them.

You can find the resulting Docker Image here: [Docker Hub Image - cgint/fah-gpu-cuda-11.7.1-base-ubuntu22.04](https://hub.docker.com/repository/docker/cgint/fah-gpu-cuda-11.7.1-base-ubuntu22.04/general)

## Ease of dockerized Folding At Home - Setup

The official version of [FAH-Docker-Image](https://hub.docker.com/r/foldingathome/fah-gpu) did not work for me as I faced the issue described as [Core 0x23 stalled on current (21.11.0) image](https://github.com/FoldingAtHome/containers/issues/31) on Github.

Thankfully https://github.com/sanori provided a patch that made things work.

And here is the result of a docker-image based on the updated version of the Dockerfile using hat fix ([Github-Repo](https://github.com/cgint/fah-gpu-docker)).
The PR from `sanori` is not yet part of an official image from `foldingathome`.

See infos regarding setup in the official repo at FAH-Docker-Image](https://hub.docker.com/r/foldingathome/fah-gpu) and maybe additionally helpful my collected infos under [https://github.com/cgint/fah-gpu-docker/docs](https://github.com/cgint/fah-gpu-docker/tree/main/docs)