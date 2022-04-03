FROM ubuntu
WORKDIR /app

# Set bazel version
ENV BAZEL_VERSION 5.1.0

# Install common packages
RUN apt-get update && apt install -y unzip gcc g++ curl git make

# Download Bazel and verify binary integrity
RUN curl -fsSLO https://github.com/bazelbuild/bazel/releases/download/${BAZEL_VERSION}/bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh
RUN curl -fsSLO https://github.com/bazelbuild/bazel/releases/download/${BAZEL_VERSION}/bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh.sha256
RUN sha256sum -c bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh.sha256

# Install Bazel
RUN mv bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh bazel-installer.sh
RUN chmod +x bazel-installer.sh && ./bazel-installer.sh

# Clean up
RUN rm bazel-installer.sh
RUN rm bazel-${BAZEL_VERSION}-installer-linux-x86_64.sh.sha256
