FROM fedora:29
LABEL maintainer "Sayan Chowdhury <gmail@yudocaa.in>"

RUN dnf install fedora-workstation-repositories -y \
    && dnf install python3-dnf-plugins-core -y \
    && dnf config-manager --set-enabled google-chrome \
    && dnf install google-chrome-stable -y \
    && systemd-machine-id-setup

RUN groupadd -f chrome && useradd -r -g chrome -G audio,video chrome \
   && mkdir -p /home/chrome/Downloads && chown -R chrome:chrome /home/chrome

COPY local.conf /etc/fonts/local.conf

USER chrome

ENTRYPOINT ["google-chrome"]
CMD ["--user-data-dir=/data"]
