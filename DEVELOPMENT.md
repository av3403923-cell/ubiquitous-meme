# Guia de Desenvolvimento - Virtus

## 🔨 Configuração do Ambiente de Desenvolvimento

```bash
# Clone e acesse o repositório
git clone https://github.com/av3403923-cell/ubiquitous-meme.git
cd ubiquitous-meme

# Crie ambiente virtual
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows

# Instale dependências de desenvolvimento
pip install -r requirements.txt
pip install black flake8 pytest pytest-cov
```

## 📁 Estrutura do Projeto

```
virtus/
├── core/           # Motor de emulação principal
│   ├── emulator.py    # Classe VirtusEmulator
│   ├── config.py      # Configurações
│   └── logger.py      # Sistema de logs
├── ui/             # Interface do usuário
│   └── main_window.py # Janela principal PyQt6
├── storage/        # Gerenciamento de armazenamento
│   └── disk.py        # Gerenciador de discos virtuais
├── network/        # Configuração de rede
│   └── network.py     # Gerenciador de rede
├── utils/          # Utilitários
│   └── system.py      # Informações do sistema
└── tests/          # Testes unitários
    └── test_emulator.py
```

## 🧪 Testes

### Executar todos os testes
```bash
pytest
```

### Testes com cobertura
```bash
pytest --cov=virtus --cov-report=html
```

### Testes específicos
```bash
pytest tests/test_emulator.py -v
```

## 🎨 Padrões de Código

### Formatação (Black)
```bash
black virtus/ tests/ main.py
```

### Análise estática (Flake8)
```bash
flake8 virtus/ tests/ main.py --max-line-length=100
```

## 📝 Exemplo de Desenvolvimento

### Adicionar Nova Feature

1. **Crie uma branch**
```bash
git checkout -b feature/minha-feature
```

2. **Implemente a feature**
```python
# Exemplo: Novo método em VirtusEmulator
def new_feature(self):
    """Descrição da feature"""
    logger.info("Implementando nova feature")
    # Implementação
    return True
```

3. **Escreva testes**
```python
# Em tests/test_emulator.py
def test_new_feature():
    """Teste a nova feature"""
    emu = VirtusEmulator()
    result = emu.new_feature()
    assert result is True
```

4. **Valide código**
```bash
black virtus/
flake8 virtus/
pytest
```

5. **Commit e Push**
```bash
git add .
git commit -m "feat: adiciona nova feature"
git push origin feature/minha-feature
```

6. **Abra Pull Request**

## 🐛 Debug

### Habilitar modo debug
```python
from virtus.core.logger import setup_logger
import logging

logger = setup_logger("virtus", level=logging.DEBUG)
```

### Usar debugger Python
```python
import pdb; pdb.set_trace()
```

## 📚 Recursos

- [QEMU Documentation](https://www.qemu.org/documentation/)
- [libvirt Documentation](https://libvirt.org/docs/)
- [PyQt6 Documentation](https://www.riverbankcomputing.com/static/Docs/PyQt6/)
- [Python Logging](https://docs.python.org/3/library/logging.html)

## 🚀 Build e Release

### Criar distribuição
```bash
python setup.py sdist bdist_wheel
```

### Publicar no PyPI (requer credenciais)
```bash
twine upload dist/*
```

## 📞 Suporte

Para dúvidas sobre desenvolvimento:
1. Abra uma issue no GitHub
2. Consulte a documentação
3. Junte-se à comunidade

---

Happy coding! 🎉
