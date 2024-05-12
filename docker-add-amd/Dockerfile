FROM cgint/fah-gpu-cuda-11.7.1-base-ubuntu22.04
LABEL description="Official Folding@home GPU Container including AMD support"

RUN wget https://repo.radeon.com/amdgpu-install/23.40.2/ubuntu/jammy/amdgpu-install_6.0.60002-1_all.deb && \
    sudo apt install -y ./amdgpu-install_6.0.60002-1_all.deb && \
    sudo apt update && \
    sudo amdgpu-install -y

COPY README.md /

WORKDIR "/fah"
VOLUME ["/fah"]
EXPOSE 7396 36330

ENTRYPOINT ["/usr/bin/FAHClient", "--chdir", "/fah"]