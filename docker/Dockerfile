FROM myoung34/github-runner

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
    curl jq \
    build-essential \
    python3 python3-pip python3-venv python3-dev \
    libssl-dev libffi-dev \
    openssh-client \
 && rm -rf /var/lib/apt/lists/*

# Optional: Node 20
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
 && apt-get install -y nodejs

COPY --chmod=+x start.sh /start.sh
ENTRYPOINT ["/start.sh"]