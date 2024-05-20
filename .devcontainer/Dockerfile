FROM nvidia/cuda:12.0.1-base-ubuntu22.04 as base

# Update default packages
RUN apt-get update

# Get Ubuntu packages
RUN apt-get install -y \
    build-essential \
    curl \
    wget \
    software-properties-common \
    gnupg

# Install CUDA toolkit (nvcc is required for bend run-cu)
RUN apt-get update && \
    apt-get install -y cuda-toolkit-11-8

# Set environment variables for CUDA
ENV CUDA_HOME=/usr/local/cuda
ENV PATH=${CUDA_HOME}/bin:${PATH}
ENV LD_LIBRARY_PATH=${CUDA_HOME}/lib64:${LD_LIBRARY_PATH}

# Update new packages
RUN apt-get update

# Get Rust
RUN curl https://sh.rustup.rs -sSf | bash -s -- -y
ENV PATH="/root/.cargo/bin:${PATH}"
# Install Rust Nightly
RUN rustup default nightly
# Install hvm and bend-lang
RUN cargo +nightly install hvm
RUN cargo +nightly install bend-lang

# Make a new Rust project
RUN cargo new bend_test