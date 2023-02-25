ARG python_image_v="python:3.10-buster"

FROM ${python_image_v}

SHELL ["/bin/bash", "-c"]

# RUN apt update && apt install -y \
#     git \
#     curl \
#     && apt --purge remove nvidia* \
#     cuda* \
#     cudnn* \
#     libnvidia* \
#     libcuda* \
#     libcudnn* 

# install cuda-toolkit
RUN wget https://developer.download.nvidia.com/compute/cuda/11.7.1/local_installers/cuda-repo-wsl-ubuntu-11-7-local_11.7.1-1_amd64.deb \
    && dpkg -i cuda-repo-wsl-ubuntu-11-7-local_11.7.1-1_amd64.deb
RUN cp /var/cuda-repo-wsl-ubuntu-11-7-local/cuda-*-keyring.gpg /usr/share/keyrings/
RUN wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-wsl-ubuntu.pin
RUN mv cuda-wsl-ubuntu.pin /etc/apt/preferences.d/cuda-repository-pin-600

# RUn apt install -y \
#     cuda-drivers \
#     cuda \
#     && autoremove \
#     && apt autoclean
#     && rm -rf /var/lib/apt/lists

ENV PATH /etc/poetry/bin:$PATH

RUN source ~/.bashrc \
    && curl -sSL https://install.python-poetry.org | POETRY_HOME=/etc/poetry python3 - 

ENV POETRY_VIRTUALENVS_CREATE=false
