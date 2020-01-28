FROM ubuntu:18.04

RUN apt-get update && apt-get install -y \
      dig \
      host \
      nslookup \
      ca-certificates \
      iputils \
      dnsutils \
      iproute2 \
      netcat \
      nc \
      nmap \
      tcpdump \
      curl \
      wget \
      jq \
      whois
RUN rm -rf /var/lib/apt/lists/*
