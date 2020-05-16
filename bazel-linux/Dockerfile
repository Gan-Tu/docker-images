FROM ubuntu
WORKDIR /app
# Install Bazel
ENV BAZEL_VERSION 3.1.0
RUN apt-get update && apt install -y unzip gcc g++ curl git
RUN curl -fsSLO https://github.com/bazelbuild/bazel/releases/download/${BAZEL_VERSION}/bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh
RUN curl -fsSLO https://github.com/bazelbuild/bazel/releases/download/${BAZEL_VERSION}/bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh.sha256
RUN mv bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh bazel-installer.sh
RUN chmod +x bazel-installer.sh && ./bazel-installer.sh
RUN rm bazel-installer.sh