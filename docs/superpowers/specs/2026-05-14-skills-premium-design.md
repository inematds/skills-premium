# Skills Premium — Design Spec

**Data:** 2026-05-14  
**Repo:** https://github.com/inematds/skills-premium  
**Deploy:** GitHub Pages  
**Formato:** INEMA.CLUB (Hub e Spoke)

---

## Visão Geral

Curso sobre como construir, otimizar e manter skills de alta qualidade no Claude Code. Conteúdo baseado em 8 dicas práticas e conceitos fundamentais de engenharia de skills.

**Emoji do curso:** ⚡  
**Total de páginas:** 24 (1 landing + 3 trilha-index + 20 módulos)

---

## Estrutura de Arquivos

```
skills-premium/
├── index.html                      # Landing page
└── curso/
    ├── trilha1/                    # Fundamentos (Emerald)
    │   ├── index.html
    │   ├── modulo-1-1.html
    │   ├── modulo-1-2.html
    │   ├── modulo-1-3.html
    │   ├── modulo-1-4.html
    │   ├── modulo-1-5.html
    │   └── modulo-1-6.html
    ├── trilha2/                    # Dicas Técnicas (Blue)
    │   ├── index.html
    │   ├── modulo-2-1.html
    │   ├── modulo-2-2.html
    │   ├── modulo-2-3.html
    │   ├── modulo-2-4.html
    │   ├── modulo-2-5.html
    │   ├── modulo-2-6.html
    │   ├── modulo-2-7.html
    │   └── modulo-2-8.html
    └── trilha3/                    # No Expert (Purple)
        ├── index.html
        ├── modulo-3-1.html
        ├── modulo-3-2.html
        ├── modulo-3-3.html
        ├── modulo-3-4.html
        ├── modulo-3-5.html
        └── modulo-3-6.html
```

---

## Trilha 1 — Fundamentos (Emerald) — Iniciantes

| Módulo | Emoji | Título | Foco |
|--------|-------|--------|------|
| 1.1 | ⚠️ | O Problema do Excesso | Por que mais skills = mais confusão. Contexto entupido, misfire, risco de segurança. |
| 1.2 | 🧠 | Nem Tudo Deve Ser Skill | Quando usar Rule, Claude.md, CLI ou automação em vez de skill. |
| 1.3 | 🏗️ | Anatomia de uma Skill que Funciona | Nome único, descrição com gatilho, progressive disclosure, UX de entrevista. |
| 1.4 | 🎯 | Como o Claude Escolhe uma Skill | Como triggers funcionam na prática — por que skills com nomes parecidos colidem. |
| 1.5 | 📂 | Progressive Disclosure | Dividir a skill em seções que o Claude só lê quando precisa — menos ruído, mais precisão. |
| 1.6 | 🚀 | Sua Primeira Skill do Zero | Passo a passo: do zero ao primeiro invoke funcionando, com exemplo real. |

---

## Trilha 2 — Dicas Técnicas (Blue) — Intermediários

| Módulo | Emoji | Título | Conceito central |
|--------|-------|--------|-----------------|
| 2.1 | 🧊 | Rode a Frio | Teste com prompt vago para validar unicidade e trigger |
| 2.2 | 📏 | Orçamento de Descrição | Limite de chars, truncamento, gatilho sempre no início |
| 2.3 | 🎤 | Faça a Skill Perguntar | Ask User Input Tool — entrevista antes de agir |
| 2.4 | ✍️ | Regras de Tom e Escrita | Anti-sycophancy, sem m-dash, tonalidade programada |
| 2.5 | ⭐ | Nota da Experiência | Skill pede avaliação 1-10 e o porquê da nota |
| 2.6 | 🔄 | Feedback que Transforma | Reverse meta prompting para evoluir a skill continuamente |
| 2.7 | 🔀 | Primitiva Errada | Skill vs Rule vs Claude.md vs CLI vs Automação |
| 2.8 | 🔍 | Auditoria Séria | Claude-code-guide agent + checklist estrutural completo |

---

## Trilha 3 — No Expert (Purple) — Experts

| Módulo | Emoji | Título | Entrega |
|--------|-------|--------|---------|
| 3.1 | 📋 | Templates Prontos | Skills modelo prontas para copiar: entrevista, reflexão, consolidação |
| 3.2 | 💥 | Prompts Canhão | Reverse meta prompting + auditoria com claude-code-guide agent |
| 3.3 | 🤖 | Sub-agentes para Testar | Como usar sub-agentes para battle test antes de usar em produção |
| 3.4 | 🧹 | Consolidação de Skills | Identificar sobreposições e fundir skills redundantes com Skill Creator 2.0 |
| 3.5 | 📊 | Stack Lean de Skills | Manter biblioteca enxuta — critérios de corte, quando deletar |
| 3.6 | 🔁 | Skills que se Melhoram Sozinhas | Bake-in de reflexão, avaliação e auto-iteração dentro da própria skill |

---

## Regras de Design (INEMA.CLUB)

- **Trilha 1:** Emerald (`text-emerald-400`, `bg-emerald-500/20`, `border-emerald-500/30`)
- **Trilha 2:** Blue (`text-blue-400`, `bg-blue-500/20`, `border-blue-500/30`)
- **Trilha 3:** Purple (`text-purple-400`, `bg-purple-500/20`, `border-purple-500/30`)
- Mínimo 6 tópicos por módulo
- Botões sempre à esquerda (`justify-start`)
- Números em círculo (não setas)
- 3 seções por tópico: O que é / Por que / Conceitos-chave
- INEMA.CLUB presente em todas as páginas (`text-sky-400`)
- Light mode CSS completo obrigatório
- Navegação Rápida obrigatória no index de cada trilha
- Botão "Ver Completo" em cada card de módulo

## Ilustrações

Os infográficos do `/doc` são integrados nos módulos:
- `23_53_27.png` (Entupiu o contexto) → módulo 1.1
- `23_53_33.png` (Truncamento da descrição) → módulo 2.2
- `23_53_39.png` (Loop morto) → módulo 2.3
- `23_53_45.png` (Nem tudo deve ser skill) → módulo 1.2
- `23_53_52.png` (Skill ideal) → módulo 1.3
- `23_53_14.png` (Visão geral 8 dicas) → landing page / trilha 2 index
- `23_59_00.png` (Playbook de poda) → módulo 2.8 / 3.5

## Notificação

Ao concluir deploy: executar `/home/nmaldaner/projetos/openpcbot/scripts/notify.sh` com mensagem de conclusão.
