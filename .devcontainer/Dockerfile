# Usa una imagen base de Ubuntu
FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Instalar dependencias del sistema
RUN apt-get update && apt-get install -y \
    curl \
    git \
    unzip \
    xz-utils \
    libglu1-mesa \
    && apt-get clean

# Instalar Flutter
RUN git clone https://github.com/flutter/flutter.git /usr/local/flutter
ENV PATH="/usr/local/flutter/bin:/usr/local/flutter/bin/cache/dart-sdk/bin:${PATH}"

# Ejecutar flutter doctor para pre-descargar dependencias
RUN flutter doctor -v

# Establecer permisos para flutter en Codespaces
RUN chown -R vscode:vscode /usr/local/flutter
