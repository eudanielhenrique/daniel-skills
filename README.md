# daniel-skills

Skills operacionais para o [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

---

### Skills disponíveis

| Skill | O que faz |
|---|---|
| `/dh-firestore-backup` | Exporta collections do Firestore para JSON |
| `/dh-firestore-restore` | Restaura dados no Firestore a partir de JSON |

---

### Instalação

```bash
git clone https://github.com/eudanielhenrique/daniel-skills.git ~/.claude/skills/daniel-skills && cd ~/.claude/skills/daniel-skills && chmod +x setup && ./setup
```

### Atualização

```bash
cd ~/.claude/skills/daniel-skills && git pull && ./setup
```

### Desinstalação

```bash
for s in dh-firestore-backup dh-firestore-restore; do rm -rf ~/.claude/skills/$s; done && rm -rf ~/.claude/skills/daniel-skills
```

---

MIT — Daniel Henrique
