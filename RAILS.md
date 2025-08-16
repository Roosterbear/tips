<h1 style="color:#c1121f">RAILS</h1>

- [Introducción](#introducción)
- [Script para WSL](#script-para-wsl)

# Introducción

# Script para WSL

```bash
#!/usr/bin/env bash

# === Actualizamos sistema ===
sudo apt update -y
sudo apt upgrade -y

# === Herramientas de compilación básicas ===
sudo apt install -y build-essential pkg-config git curl wget

# === Dependencias para compilar Ruby ===
sudo apt install -y \
  libssl-dev zlib1g-dev libreadline-dev bison autoconf \
  libyaml-dev libxml2-dev libffi-dev libgdbm-dev

# === Bases de datos (elige las que uses, aquí van todas) ===
sudo apt install -y libsqlite3-dev libpq-dev libmysqlclient-dev

# === Herramientas JS (necesarias para Rails 7+) ===
sudo apt install -y nodejs npm
sudo npm install --global yarn

# === Extra útiles ===
sudo apt install -y imagemagick libmagickwand-dev libvips redis-server

# === Instalamos rbenv (si no lo tienes aún) ===
if [ ! -d "$HOME/.rbenv" ]; then
  echo "Instalando rbenv..."
  git clone https://github.com/rbenv/rbenv.git ~/.rbenv
  echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
  echo 'eval "$(rbenv init - bash)"' >> ~/.bashrc
  git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
  source ~/.bashrc
fi

# === Instalamos Ruby (ejemplo: 3.1.2, cámbialo si quieres otra versión) ===
rbenv uninstall -f 3.1.2 || true
rbenv install 3.1.2
rbenv global 3.1.2

# === Aseguramos que se cargue rbenv

echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init - bash)"' >> ~/.bashrc
source ~/.bashrc

# === Instalamos Bundler y Rails ===
gem install bundler
gem install rails
rbenv rehash

echo "✅ Entorno Rails listo en WSL con Ruby $(ruby -v) y Rails $(rails -v)"

```
























