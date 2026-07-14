# daniel-skills

Skills operacionais para o [Claude Code](https://docs.anthropic.com/en/docs/claude-code). Construídas para uso real no dia a dia — não são abstrações, são comandos que executam trabalho concreto.

---

### O problema

Toda vez que você precisa fazer um backup ou restore do Firestore, você volta ao zero: procura a documentação, lembra qual pacote usar, escreve o script na mão, torce pra não errar o projeto. O processo é simples mas frágil — e quando você precisa de um restore, geralmente está sob pressão.

`daniel-skills` resolve isso. O processo vira um comando. O comando vira confiança.

---

### Skills disponíveis

| Skill | Quando usar | O que faz |
|---|---|---|
| `/firestore-backup` | Antes de uma mudança arriscada, agendado, ou sempre que precisar | Conecta no Firestore, exporta collections para JSON, confirma o que foi salvo |
| `/firestore-restore` | Recovery, migração entre ambientes, ou desfazer uma mudança ruim | Lê o JSON de backup, restaura no Firestore com conversão correta de tipos, confirma antes de executar |

---

### Pré-requisitos

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
- Node.js 18+
- `firestore-export-import` instalado no projeto:

```bash
npm install github:eudanielhenrique/firestore-backup-restore#fix/v1.7.0-batch-writes-data-types
```

- `serviceAccountKey.json` na raiz do projeto (Firebase Console → Project Settings → Service accounts → Generate new private key)

---

### Instalação

```bash
git clone https://github.com/eudanielhenrique/daniel-skills.git ~/.claude/skills/daniel-skills && cd ~/.claude/skills/daniel-skills && chmod +x setup && ./setup
```

---

### Uso

```
/firestore-backup
```
O Claude pergunta quais collections, verifica as credenciais, executa o backup e confirma o arquivo gerado.

```
/firestore-restore
```
O Claude lista os backups disponíveis, confirma o destino, detecta os tipos de dados e executa o restore com segurança.

---

### Atualização

```bash
cd ~/.claude/skills/daniel-skills && git pull && ./setup
```

### Desinstalação

```bash
rm -f ~/.claude/skills/firestore-backup ~/.claude/skills/firestore-restore
rm -rf ~/.claude/skills/daniel-skills
```

---

MIT — Daniel Henrique
