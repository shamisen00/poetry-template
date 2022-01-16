FROM ubuntu:20.04

SHELL ["/bin/bash", "-c"]

# [Optional] Uncomment this section to install additional OS packages.
RUN apt update && apt install -y python3 \
    python3-distutils \
    git \
    curl \
    && rm -rf /var/lib/apt/lists
#   && apt-get -y install --no-install-recommends <your-package-list-here>

RUN echo "alias python='python3' " >> ~/.bashrc 

RUN source ~/.bashrc \
    && curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python3 - \
    && source $HOME/.poetry/env \
    && poetry config virtualenvs.in-project true
    # COPY . .
    # && poetry install