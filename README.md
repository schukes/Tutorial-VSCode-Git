# Guia Rápido: Configuração do VS Code + Git + IA (Claude & Gemini)

Resumo direto das configurações do ambiente para desenvolvimento em **Java** e **CSS** com Git e Inteligência Artificial integrados.

---

## 1. Instalação e Identidade do Git no Windows

Instalar o Git via terminal (PowerShell) e configurar usuário:

```powershell
winget install --id Git.Git -e --source winget
git config --global user.name "Nome Sobrenome"
git config --global user.email "email@gmail.com"
```

---

## 2. Extensões Essenciais no VS Code (`Ctrl + Shift + X`)

- **Java:** `Extension Pack for Java`
- **CSS / Formatação:** `Prettier - Code formatter`
- **Visual e Erros:** `Material Icon Theme` e `Error Lens`
- **Git e GitHub:** `GitLens`, `Git Graph` e `GitHub Pull Requests`
- **Inteligência Artificial:** `GitHub Copilot` (para usar o Claude) e `Continue` (para usar o Gemini)

---

## 3. Como Conectar e Usar o Git no VS Code (`Ctrl + Shift + G`)

- **Baixar projeto do GitHub (Clonar):** Aba _Source Control_ (`Ctrl + Shift + G`) > **Clone Repository** > **Clone from GitHub** > Escolher o projeto e a pasta no PC.
- **Subir projeto novo para o GitHub:** Abrir pasta no VS Code (**File > Open Folder**) > Aba _Source Control_ (`Ctrl + Shift + G`) > **Publish to GitHub** (escolher _Private_ ou _Public_).
- **Salvar alterações no dia a dia:**
  1. Alterar e salvar os arquivos (`Ctrl + S`).
  2. Na aba _Source Control_ (`Ctrl + Shift + G`), clicar nas estrelinhas (`✨`) para gerar a mensagem de commit com IA (ou digitar manualmente).
  3. Clicar em **Commit** e depois em **Sync Changes** (Push).

---

## 4. Configuração das IAs Gratuitas

### A. Claude (via GitHub Copilot Free)

1. Ativar o plano gratuito em: `https://github.com/settings/copilot`
2. Abrir o chat no VS Code (`Ctrl + Alt + I`) e selecionar o modelo **Claude** no canto inferior do chat.

### B. Gemini (via Extensão Continue)

1. Gerar chave gratuita em: `https://aistudio.google.com/apikey`
2. Abrir configurações do Continue (`C:\Users\tiago\.continue\config.yaml`) e colar:

```yaml
name: Main Config
version: 1.0.0
schema: v1
models:
  - name: Gemini 2.5 Flash
    provider: gemini
    model: gemini-2.5-flash
    apiKey: SUA_CHAVE_AQUI
    roles:
      - chat
      - edit
      - apply
      - autocomplete
  - name: Gemini 2.5 Pro
    provider: gemini
    model: gemini-2.5-pro
    apiKey: SUA_CHAVE_AQUI
    roles:
      - chat
      - edit
      - apply
```

---

## 5. Configurações do Editor (`settings.json`)

Abrir com `Ctrl + Shift + P` > **Preferences: Open User Settings (JSON)** e colar:

```json
{
  "files.autoSave": "onFocusChange",
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "editor.wordWrap": "on",
  "editor.minimap.enabled": false,
  "workbench.iconTheme": "material-icon-theme",
  "java.saveActions.organizeImports": true,
  "[java]": {
    "editor.tabSize": 4,
    "editor.defaultFormatter": "redhat.java"
  },
  "[css]": {
    "editor.tabSize": 2,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "errorLens.enabledDiagnosticLevels": ["error", "warning"],
  "git.autofetch": true,
  "git.confirmSync": false,
  "git.enableSmartCommit": true,
  "gitlens.codeLens.enabled": false
}
```
