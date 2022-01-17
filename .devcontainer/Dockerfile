FROM ubuntu:20.04

SHELL ["/bin/bash", "-c"]

# to avoid selecting timezone on installing packages.
ENV DEBIAN_FRONTEND=noninteractive

# [Optional] Uncomment this section to install additional OS packages.
# python-opencv is just python wrapper of opencv. So, you need to install libraries that are dependent on opencv.
RUN apt update && apt install -y python3 \
    python3-distutils \
    git \
    curl \
    libgl1-mesa-dev \
    libglib2.0-0 \
    && rm -rf /var/lib/apt/lists
#   && apt-get -y install --no-install-recommends <your-package-list-here>

RUN echo "alias python='python3' " >> ~/.bashrc 

RUN source ~/.bashrc \
    && curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python3 - \
    && source $HOME/.poetry/env \
    && poetry config virtualenvs.in-project true
    # COPY . .
    # && poetry install

RUN echo "source $HOME/.poetry/env" >> ~/.bashrc