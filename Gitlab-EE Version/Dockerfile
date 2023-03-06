FROM ubuntu:20.04
ARG DEBIAN_FRONTEND=noninteractive
RUN apt update
RUN apt upgrade -y
RUN apt install -y curl
RUN apt install -y ca-certificates
RUN apt install -y curl
RUN apt install -y openssh-server
RUN curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | bash
RUN apt -y install gitlab-ee
RUN curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | bash
CMD gitlab-ctl reconfigure & /opt/gitlab/embedded/bin/runsvdir-start 
EXPOSE 443 80 22