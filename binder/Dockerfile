FROM intel4coro/base-notebook:20.04-noetic-vnc

# Path to the default ROS workspace
ENV ROS_WS=${HOME}/workspace/ros

# Evita prompts interativos
ENV DEBIAN_FRONTEND=noninteractive

#============= Install extra software packages =============#
# Examples:
# RUN apt update && apt install -y curl
# RUN pip install numpy
#===========================================================#

# Copy content to the image
ENV REPO_DIR=${HOME}/work
WORKDIR ${REPO_DIR}
COPY --chown=${NB_USER}:users . ${REPO_DIR}/

# Create a symbolic link to the ROS workspace under the working directory
RUN ln -s ${ROS_WS} ${PWD}/ROS_WS

# The entrypoint of the docker image
COPY --chown=${NB_USER}:users binder/entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]


# FROM osrf/ros:noetic-desktop-full

# # Evita prompts interativos
# ENV DEBIAN_FRONTEND=noninteractive

# # Cria usuário padrão para Binder
# ARG NB_USER=jovyan
# ARG NB_UID=1000
# ENV HOME=/home/${NB_USER}

# # Instala dependências do sistema
# RUN apt-get update && \
#     apt-get install -y sudo python3-pip git python-is-python3 \
#     ros-noetic-ros-tutorials \
#     python3-catkin-tools \
#     && apt-get clean && rm -rf /var/lib/apt/lists/*

# # Cria usuário com permissões sudo
# RUN useradd -m -s /bin/bash -N -u $NB_UID $NB_USER && \
#     echo "${NB_USER} ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/${NB_USER}

# # Instala Jupyter Notebook
# RUN pip3 install notebook jupyterlab

# # Define usuário e diretório padrão
# USER $NB_USER
# WORKDIR $HOME

# # Fonte do ROS
# RUN echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc

# # Comando padrão para o Binder
# CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--NotebookApp.token=''", "--NotebookApp.allow_origin='*'"]
