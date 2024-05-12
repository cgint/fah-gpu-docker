FROM cgint/fah-gpu-cuda-11.7.1-base-ubuntu22.04
LABEL description="Official Folding@home GPU Container including AMD support"

RUN apt-get update && apt-get install -y wget
RUN wget https://repo.radeon.com/amdgpu-install/23.40.2/ubuntu/jammy/amdgpu-install_6.0.60002-1_all.deb && \
    apt install -y ./amdgpu-install_6.0.60002-1_all.deb && \
    rm amdgpu-install_6.0.60002-1_all.deb && \
    apt update && \
    amdgpu-install -y

COPY README.md /

WORKDIR "/fah"
VOLUME ["/fah"]
EXPOSE 7396 36330

ENTRYPOINT ["/usr/bin/FAHClient", "--chdir", "/fah"]