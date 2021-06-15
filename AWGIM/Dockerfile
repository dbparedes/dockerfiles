FROM tensorflow/tensorflow:1.12.0-gpu-py3

RUN apt-get update && apt-get install -y wget tree vim htop \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

# Install bazel
ARG BAZEL_VERSION=3.7.2
RUN mkdir /bazel && \
    wget -O /bazel/installer.sh "https://github.com/bazelbuild/bazel/releases/download/${BAZEL_VERSION}/bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh" && \
    wget -O /bazel/LICENSE.txt "https://raw.githubusercontent.com/bazelbuild/bazel/master/LICENSE" && \
    chmod +x /bazel/installer.sh && \
    /bazel/installer.sh && \
    rm -f /bazel/installer.sh

RUN pip install tensorflow-probability
