
FROM debian:12

ARG USERNAME=user
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
  && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
  && usermod -s /bin/bash $USERNAME \
  # Add sudo support
  && apt-get update \
  && apt-get install -y sudo \
  && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
  && chmod 0440 /etc/sudoers.d/$USERNAME

ENV DEBIAN_FRONTEND=noninteractive

#Install required packages
RUN apt update && apt install -y                         \
 ack                                                     \
 apt-utils                                               \
 build-essential                                         \
 ca-certificates                                         \
 curl                                                    \
 git                                                     \
 htop                                                    \
 locate                                                  \
 make                                                    \
 openocd                                                 \
 nano                                                    \
 openssh-client                                          \
 wget                                                    \
 cmake                                                   \
 gcc-arm-none-eabi gdb-arm-none-eabi                     \
 protobuf-compiler                                       \
 python3                                                 \
 python3-pip                                             \
&& rm -rf /var/lib/apt/lists/*



# Set the default user
USER $USERNAME