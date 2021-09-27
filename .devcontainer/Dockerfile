FROM jupyter-dev:latest

USER root

# ===== Docker ===============================================================
# Reference: https://docs.docker.com/engine/install/ubuntu/
RUN apt-get install -y  apt-transport-https                                 \
                        ca-certificates                                     \
                        curl                                                \
                        gnupg                                               \
                        lsb-release                                     &&  \
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg |               \
        gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg &&  \
    echo    "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
            $(lsb_release -cs) stable" |                                    \
            tee /etc/apt/sources.list.d/docker.list > /dev/null         &&  \
    apt-get update                                                      &&  \
    apt-get install -y  docker-ce                                           \
                        docker-ce-cli                                       \
                        containerd.io

RUN usermod -a -G docker jovyan

USER jovyan

# ===== VS Code-specific Stuff ===============================================
RUN pip install         autopep8

