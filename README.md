# auditd-docker-compose
Container for building/running auditd using docker-compose

# Required Capabilities
Audit Read

Audit Control

# PID = Host
The pid = host option is required for local logging within a container

# Recommended bind-mount options
Recommend that audit.rules and auditd.conf are bind-mounted using a read-only option, so that options can be tweaked after the image is made, and those files aren't impacted by playing with the container

# To Build and Run:
From the directory with the docker-compose.yml run

sudo docker-compose up --build

# To Run:
sudo docker-compose up
