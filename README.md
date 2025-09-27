# 🎶 FL Studio 20.8.3 no macOS Apple Silicon (M1/M2/M3) – Fix

Este repositório documenta como rodar o **FL Studio 20.8.3 (x86_64, Intel only)** em Macs com Apple Silicon usando o **Rosetta 2**.  
Versões antigas do FL Studio não possuem suporte nativo a ARM e podem exibir o seguinte erro ao abrir:

```
dlopen(.../FLEngine_x64.dylib, 0x0001): tried: ... (mach-o file, but is an incompatible architecture (have 'x86_64', need 'arm64'))
```

---

## 🚩 O problema
O macOS tenta carregar bibliotecas `arm64`, mas o FL Studio 20.8.3 foi compilado apenas para `x86_64`.  
Sem o Rosetta, o app não inicia.

---

## ✅ A solução

### 1. Instalar o Rosetta 2 (ele é a camada de compatibilidade)
No **Terminal**, execute:

```bash
softwareupdate --install-rosetta --agree-to-license
```

---

### 2. Baixar o Patch
Para facilitar, este repositório inclui um **app do Automator já configurado**:  

- **Download:** [FL Studio 20.8.3 fix](https://github.com/drizion/fl-studio-20-mac-arm-fix/releases)  
- Descompacte e mova para a pasta **Aplicativos**.  
- Abra o app com 2 cliques; ele já roda via **Rosetta x86_64**.  
- O ícone do app foi personalizado para usar o **ícone oficial do FL Studio**.
- Não exclua o app original na pasta **Aplicativos**, o Patch usa ele para iniciar.

> ⚠️ O macOS pode mostrar um aviso de “app não verificado”.  
> Para contornar:  
> 1. Vá em **Preferências do Sistema → Segurança e Privacidade → Geral**  
> 2. Clique em **Abrir mesmo assim** para o app baixado.

---

### 3. Observações
- Este fix é apenas um **workaround** para rodar o FL Studio 20 em Apple Silicon.  
- A Image-Line já oferece versões **nativas ARM (Universal)** a partir do **FL Studio 20.9.2**.  
- Atualizar para a versão ARM é recomendado para melhor performance e compatibilidade de plugins.

---

## 📌 Licença
Este repositório é apenas documentação/tutorial.  
O FL Studio é software proprietário da [Image-Line](https://www.image-line.com/).
