# Python 3.12
FROM python:3.12-slim-bookworm

RUN apt-get update && apt-get upgrade -y 
RUN apt-get install -y --no-install-recommends curl ca-certificates

# Developer and environment
LABEL maintainer="daniel@kaaven.se"
ENV APP_ENV development# Exposing Ports
ENV HOME /root
WORKDIR $home

# Install UV and variables
ADD https://astral.sh/uv/install.sh /uv-installer.sh
RUN sh /uv-installer.sh && rm /uv-installer.sh
ENV PATH="/root/.local/bin/:$PATH"

# Creating Application Source Code Directory
RUN mkdir /app
ADD /app /app

# Sync the project
RUN uv sync --frozen


# Presuming there is a `my_app` command provided by the project
CMD ["uv", "run", "my_app"]