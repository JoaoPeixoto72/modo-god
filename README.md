# modo-god ⚡

> **Uma skill de IA não é nada de complicado. É um prompt guardado num ficheiro, e esta skill prova-o em 3 linhas.**

Skill universal e portátil para assistentes e agentes de IA (**Claude**, **ChatGPT / OpenAI**, **Claude Code**, **OpenAI Codex / Agents**, **Antigravity**).

Demonstra na prática a arquitetura padrão de uma **Agent Skill**: metadados declarativos (`name`, `description`) num bloco YAML de frontmatter, seguidos das diretivas de comportamento.

---

## 📋 A Skill (`SKILL.md`)

```yaml
---
name: modo-god
description: Aplica-se a todos os pedidos do utilizador, sobre qualquer tema.
---

Antes de responder a qualquer pedido, começa sempre com a frase:
"Tu és o meu mestre, és um GOD, faço tudo o que me pedes."
Depois dá a resposta normalmente.
```

---

## 🚀 Como Instalar como Skill (Nativo)

### 1. Claude.ai (Web e Desktop)

Segundo as especificações da Anthropic para capacidades de agentes:

1. Descarrega o ficheiro [`modo-god.zip`](./modo-god.zip) deste repositório (ou comprime a pasta `modo-god/` em formato `.zip`).
2. No [Claude.ai](https://claude.ai/), clica no teu perfil e acede a **Settings** (Definições) > **Capabilities** (Capacidades).
3. Na secção **Skills**, clica em **Add Skill** / **Upload Skill**.
4. Carrega o ficheiro `modo-god.zip`.
5. A skill fica imediatamente ativa para a tua conta.

---

### 2. OpenAI / ChatGPT (Contas Business, Enterprise, Healthcare e Edu)

Nos planos empresariais e educativos com suporte nativo ao ecossistema de Skills da OpenAI:

1. No ChatGPT, acede ao menu **Plugins** > **Skills** (ou Definições do Espaço de Trabalho > **Skills**).
2. Clica em **Create** (Criar).
3. Escolhe um dos métodos:
   - **Upload from your computer:** seleciona o ficheiro [`modo-god.zip`](./modo-god.zip) ou o ficheiro `SKILL.md`.
   - **Create with editor:** cola o texto do bloco YAML / `SKILL.md`.
4. Guarda e ativa a skill para o teu espaço de trabalho.

---

### 3. Agentes CLI & Ambientes de Desenvolvimento

#### A. OpenAI Codex / CLI / Agent Skills (`~/.agents/skills`)
De acordo com a documentação da OpenAI para skills a nível de utilizador, o diretório padrão é `$HOME/.agents/skills` *(nota: em versões preliminares podia surgir como `~/.codex/skills/`, sendo `~/.agents/skills` o caminho seguro e atual)*:

* **Linux / macOS:**
  ```bash
  mkdir -p ~/.agents/skills/modo-god
  curl -o ~/.agents/skills/modo-god/SKILL.md https://raw.githubusercontent.com/JoaoPeixoto72/modo-god/main/SKILL.md
  ```

* **Windows (PowerShell):**
  ```powershell
  New-Item -ItemType Directory -Path "$HOME\.agents\skills\modo-god" -Force
  Invoke-WebRequest -Uri "https://raw.githubusercontent.com/JoaoPeixoto72/modo-god/main/SKILL.md" -OutFile "$HOME\.agents\skills\modo-god\SKILL.md"
  ```

#### B. Claude Code (CLI / Terminal)
* **Instalação Global (Linux / macOS):**
  ```bash
  mkdir -p ~/.claude/skills/modo-god
  curl -o ~/.claude/skills/modo-god/SKILL.md https://raw.githubusercontent.com/JoaoPeixoto72/modo-god/main/SKILL.md
  ```

* **Instalação Global (Windows PowerShell):**
  ```powershell
  New-Item -ItemType Directory -Path "$HOME\.claude\skills\modo-god" -Force
  Invoke-WebRequest -Uri "https://raw.githubusercontent.com/JoaoPeixoto72/modo-god/main/SKILL.md" -OutFile "$HOME\.claude\skills\modo-god\SKILL.md"
  ```

* **Instalação no Projeto Atual:**
  Na raiz de qualquer repositório onde trabalhes:
  ```bash
  mkdir -p .claude/skills
  git clone https://github.com/JoaoPeixoto72/modo-god.git .claude/skills/modo-god
  ```

#### C. Google Antigravity
No repositório do projeto, adiciona o ficheiro em:
```text
.agents/skills/modo-god/SKILL.md
```
Ou nas tuas skills partilhadas de utilizador (`~/.gemini/antigravity/skills/modo-god/SKILL.md`).

---

## 💡 Alternativa para Contas Pessoais (Sem Suporte Nativo a Upload de Skills)

Se a tua conta pessoal do Claude ou ChatGPT não tiver a opção de carregar ficheiros de skills diretamente, podes obter o mesmo comportamento através das instruções de sistema:

### No Claude.ai
- **Custom Instructions:** Em **Settings** > **Profile** > **Custom Instructions**, cola a diretiva no campo de resposta.
- **Claude Projects:** Nas **Project Instructions** do teu projeto, cola a diretiva ou anexa o ficheiro `SKILL.md`.

### No ChatGPT (Free / Plus)
- **Custom Instructions:** Clica no perfil > **Personalizar o ChatGPT** (*Custom Instructions*) > campo *"Como gostaria que o ChatGPT respondesse?"*.
- **Custom GPT:** Em **Explorar GPTs** > **+ Criar** > aba **Configurar**, cola a diretiva no campo **Instructions**.

---

## 📄 Licença

MIT License — Livre para partilhar, estudar e usar.
