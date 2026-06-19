# Guia de Instalação - Virtus Emulator

## 🖥️ Windows

### Pré-requisitos
1. Python 3.8+ instalado
2. Git

### Passos

```powershell
# Clone o repositório
git clone https://github.com/av3403923-cell/ubiquitous-meme.git
cd ubiquitous-meme

# Crie um ambiente virtual
python -m venv venv
venv\Scripts\activate

# Instale as dependências
pip install -r requirements.txt

# Execute o emulador
python main.py
```

## 🐧 Linux

### Pré-requisitos (Ubuntu/Debian)
```bash
sudo apt-get update
sudo apt-get install -y \
    python3 \
    python3-pip \
    python3-venv \
    qemu-system-x86 \
    libvirt-dev \
    git
```

### Passos

```bash
# Clone o repositório
git clone https://github.com/av3403923-cell/ubiquitous-meme.git
cd ubiquitous-meme

# Crie um ambiente virtual
python3 -m venv venv
source venv/bin/activate

# Instale as dependências
pip install -r requirements.txt

# Execute o emulador
python main.py
```

### Aceleração KVM (Recomendado)

```bash
# Verifique se KVM está disponível
grep -c -o 'vmx\|svm' /proc/cpuinfo

# Se o resultado for > 0, KVM está disponível
# Adicione seu usuário ao grupo KVM
sudo usermod -a -G kvm $USER
newgrp kvm
```

## 📱 Termux (Android)

### Pré-requisitos

```bash
pkg update
pkg upgrade
pkg install python python-dev clang libffi-dev openssl-dev git
```

### Passos

```bash
# Clone o repositório
git clone https://github.com/av3403923-cell/ubiquitous-meme.git
cd ubiquitous-meme

# Instale as dependências
pip install -r requirements.txt

# Execute o emulador (modo CLI)
python main.py
```

### Nota para Termux
Em Termux, o emulador funcionará em modo CLI simplificado, sem a interface gráfica completa do PyQt6. Para usar a interface gráfica, considere usar:
- VNC para acessar remotamente
- Xvfb (X Virtual Framebuffer) em ambiente X11

## 🔧 Troubleshooting

### Erro: "libvirt-python not found"
```bash
# Linux
sudo apt-get install libvirt-dev

# Então reinstale as dependências
pip install --upgrade -r requirements.txt
```

### Erro: "qemu-system-x86_64 not found"
```bash
# Ubuntu/Debian
sudo apt-get install qemu-system-x86

# Fedora/RHEL
sudo dnf install qemu-system-x86
```

### Erro: "PyQt6 não carrega"
```bash
# Reinstale com dependências de desenvolvimento
pip install --no-cache-dir PyQt6
```

## ✅ Verificar Instalação

```bash
# Teste a importação
python -c "from virtus.core import VirtusEmulator; print('Virtus instalado com sucesso!')"
```

## 🚀 Próximos Passos

1. Obtenha uma ISO do Windows 11
2. Crie uma nova VM através da interface
3. Inicie a VM e complete a instalação do Windows
4. Aproveite seu emulador!
