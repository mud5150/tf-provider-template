FROM hashicorp/terraform:latest as terraform
FROM golang:1.21.1 as tfdev
ARG DEBIAN_FRONTEND=noninteractive
# Install curl
RUN apt-get update && apt-get install -y --no-install-recommends curl=7* && \
    apt-get clean
RUN curl -sL https://aka.ms/InstallAzureCLIDeb | bash

# Install make
RUN apt-get update && apt-get install --no-install-recommends -y make=4* && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
# Install staticcheck, godebugger,cobracli, gopls,gocode,godef for vscode
RUN go install golang.org/x/tools/gopls@latest && \
    go install -v github.com/go-delve/delve/cmd/dlv@latest && \
    go install honnef.co/go/tools/cmd/staticcheck@latest
# install terraform
COPY --from=terraform /bin/terraform /bin/terraform
ENV GOBIN=/go/bin
CMD ["bash"]