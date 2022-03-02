 # mcr.microsoft.com/vscode/devcontainers/go:0-1-bullseye
FROM mcr.microsoft.com/vscode/devcontainers/go@sha256:4cae6b242e4c6357f3242c0c6c70987cf56ad42e7c3ae925ea3ad3525925f891

ARG NODE_VERSION="lts/*"
RUN if [ "${NODE_VERSION}" != "none" ]; then su vscode -c ". /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi

ARG BAZEL_BUILDTOOLS_VERSION=5.0.1
ARG BAZEL_BUILDTOOLS_URL="https://github.com/bazelbuild/buildtools/releases/download/"
RUN curl -sSL "${BAZEL_BUILDTOOLS_URL}/${BAZEL_BUILDTOOLS_VERSION}/buildozer-linux-amd64" > /usr/local/bin/buildozer && \
    curl -sSL "${BAZEL_BUILDTOOLS_URL}/${BAZEL_BUILDTOOLS_VERSION}/buildifier-linux-amd64" >  /usr/local/bin/buildifier && \
    chmod +x /usr/local/bin/buildozer && \
    chmod +x /usr/local/bin/buildifier
