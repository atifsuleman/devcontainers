# Start from a base dev container image
FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Install build dependencies, tmux, stow
RUN apt-get update && \
    apt-get install -y \
      ninja-build gettext cmake curl build-essential git tmux stow && \
    rm -rf /var/lib/apt/lists/*

# Clone and build Neovim (latest stable)
RUN git clone https://github.com/neovim/neovim.git /tmp/neovim && \
    cd /tmp/neovim && \
    git checkout stable && \
    make CMAKE_BUILD_TYPE=Release && \
    make install && \
    rm -rf /tmp/neovim