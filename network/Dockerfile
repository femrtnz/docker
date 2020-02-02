FROM ubuntu:18.04

RUN apt-get update && apt-get install -y \
      ca-certificates \
      dnsutils \
      iproute2 \
      netcat \
      nmap \
      tcpdump \
      curl \
      wget \
      jq \
      whois
RUN rm -rf /var/lib/apt/lists/*
