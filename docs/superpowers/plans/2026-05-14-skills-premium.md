# Skills Premium — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Criar curso completo Skills Premium no formato INEMA.CLUB com 24 páginas HTML e fazer deploy no GitHub Pages do repo `inematds/skills-premium`.

**Architecture:** Hub e Spoke — landing page → 3 trilha-index → 20 páginas de módulo. Todas as páginas seguem o design system INEMA.CLUB (dark/light mode, Tailwind CDN, navegação global, componentes padronizados).

**Tech Stack:** HTML puro, Tailwind CSS (CDN), JavaScript vanilla, GitHub Pages

---

## Referências Obrigatórias

Antes de criar qualquer página, ler:
- `/home/nmaldaner/.claude/skills/formato-curso/references/MASTER_COMPLETO.md` — templates HTML completos
- `/home/nmaldaner/.claude/skills/formato-curso/references/CHECKLIST_REVISAO.md` — checklist de revisão

## Estrutura de Arquivos

```
/home/nmaldaner/projetos/skills-premium/
├── index.html
├── doc/                          (já existe — imagens dos infográficos)
└── curso/
    ├── trilha1/
    │   ├── index.html
    │   ├── modulo-1-1.html ... modulo-1-6.html
    ├── trilha2/
    │   ├── index.html
    │   ├── modulo-2-1.html ... modulo-2-8.html
    └── trilha3/
        ├── index.html
        ├── modulo-3-1.html ... modulo-3-6.html
```

## Cores por Trilha
- T1 Fundamentos: `emerald` (`text-emerald-400`, `bg-emerald-500/20`, `border-emerald-500/30`, `from-emerald-900/30`)
- T2 Dicas Técnicas: `blue` (`text-blue-400`, `bg-blue-500/20`, `border-blue-500/30`, `from-blue-900/30`)
- T3 No Expert: `purple` (`text-purple-400`, `bg-purple-500/20`, `border-purple-500/30`, `from-purple-900/30`)

---

### Task 1: Git setup e estrutura de diretórios

**Files:**
- Create: `curso/trilha1/`, `curso/trilha2/`, `curso/trilha3/`

- [ ] **Step 1: Inicializar git e conectar ao remote**

```bash
cd /home/nmaldaner/projetos/skills-premium
git init
git remote add origin https://github.com/inematds/skills-premium.git
```

- [ ] **Step 2: Criar estrutura de diretórios**

```bash
mkdir -p curso/trilha1 curso/trilha2 curso/trilha3
```

- [ ] **Step 3: Criar .gitignore**

```bash
echo ".DS_Store" > .gitignore
```

---

### Task 2: Landing Page — index.html

**Files:**
- Create: `index.html`

O index usa cores de TODAS as trilhas. Incluir todos os overrides de light mode (emerald, blue, purple e hover variants).

**Estrutura da landing page:**
- Nav com logo ⚡ Skills Premium + link INEMA.CLUB (sky-400) + links para as 3 trilhas
- Hero: título, subtítulo, 3 stats (20 módulos, 3 trilhas, nível iniciante ao expert)
- Seção "3 Trilhas" — 3 cards grandes (emerald, blue, purple) com lista de módulos de cada
- CTA final
- Footer com INEMA.CLUB

- [ ] **Step 1: Criar index.html seguindo Sec. 8.1 do MASTER como base**

Usar template base da Sec. 8.1, adaptando para landing page com as 3 trilhas.

- [ ] **Step 2: Verificar com CHECKLIST_REVISAO.md**

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "feat: landing page"
```

---

### Task 3: Trilha 1 — Index (Fundamentos / Emerald)

**Files:**
- Create: `curso/trilha1/index.html`

**Conteúdo:**
- Badge: TRILHA 1
- Título: ⚠️ Fundamentos de Skills
- Stats: 6 Módulos, 36+ Tópicos, ~3h, Iniciante
- Navegação Rápida (OBRIGATÓRIA): grid 2 colunas com 6 cards-âncora
- 6 Cards de Módulo com tópicos expansíveis (mínimo 6 tópicos cada):

**Módulo 1.1 — ⚠️ O Problema do Excesso** (~35 min)
Tópicos: 1. A ilusão de cobertura | 2. Como skills entopem o contexto | 3. O peso invisível dos tokens | 4. Risco de segurança em skills externas | 5. Skills desatualizadas e o efeito fantasma | 6. Menos skills, mais resultado

**Módulo 1.2 — 🧠 Nem Tudo Deve Ser Skill** (~30 min)
Tópicos: 1. A armadilha do "tem skill pra isso" | 2. Quando usar uma Rule | 3. Quando usar o Claude.md | 4. Quando usar CLI ou automação | 5. Quando uma API é melhor | 6. O critério de decisão correto

**Módulo 1.3 — 🏗️ Anatomia de uma Skill que Funciona** (~40 min)
Tópicos: 1. Nome claro e único | 2. Descrição com gatilho | 3. Progressive disclosure | 4. UX de entrevista | 5. Reflexão no final | 6. A skill como escultura em argila

**Módulo 1.4 — 🎯 Como o Claude Escolhe uma Skill** (~30 min)
Tópicos: 1. Como o sistema de triggers funciona | 2. O que o Claude vê no carregamento | 3. Colisão entre skills similares | 4. O papel do nome vs. descrição | 5. Testando a escolha do Claude | 6. Corrigindo ambiguidades de trigger

**Módulo 1.5 — 📂 Progressive Disclosure** (~35 min)
Tópicos: 1. O que é progressive disclosure | 2. Por que seções nomeadas importam | 3. Estrutura de seções num arquivo skill | 4. Exemplo: skill com e sem disclosure | 5. Quando o Claude lê cada seção | 6. Reduzindo hallucinations com disclosure

**Módulo 1.6 — 🚀 Sua Primeira Skill do Zero** (~45 min)
Tópicos: 1. Escolhendo o caso de uso certo | 2. Escrevendo o frontmatter YAML | 3. Escrevendo o corpo da skill | 4. Primeiro teste de invoke | 5. Ajustando com base no resultado | 6. Exemplo completo comentado

- [ ] **Step 1: Criar curso/trilha1/index.html com todos os 6 cards e Navegação Rápida**
- [ ] **Step 2: Verificar checklist**
- [ ] **Step 3: Commit**

```bash
git add curso/trilha1/index.html
git commit -m "feat: trilha1 index"
```

---

### Task 4: Trilha 1 — Módulos 1.1 a 1.6

**Files:**
- Create: `curso/trilha1/modulo-1-1.html` até `curso/trilha1/modulo-1-6.html`

Cada módulo segue Sec. 6.2 do MASTER. Mínimo 6 tópicos, cada tópico com:
- Número em círculo grande (w-12 h-12)
- Parágrafo introdutório
- Box Conceito Principal (gradiente emerald)
- Box Dica Prática (primary/yellow)
- Grid Fazer vs Evitar (emerald/red) quando aplicável
- Resumo final com checklist

**Imagens a incorporar:**
- `modulo-1-1.html`: embed do infográfico `doc/ChatGPT Image 13 de mai. de 2026, 23_53_27.png` (Entupiu o Contexto)
- `modulo-1-2.html`: embed do infográfico `doc/ChatGPT Image 13 de mai. de 2026, 23_53_45.png` (Nem tudo deve ser skill)
- `modulo-1-3.html`: embed do infográfico `doc/ChatGPT Image 13 de mai. de 2026, 23_53_52.png` (Skill ideal)

Path relativo das imagens a partir de `curso/trilha1/`: `../../doc/[nome-da-imagem]`

- [ ] **Step 1: Criar modulo-1-1.html (O Problema do Excesso)**
- [ ] **Step 2: Criar modulo-1-2.html (Nem Tudo Deve Ser Skill)**
- [ ] **Step 3: Criar modulo-1-3.html (Anatomia de uma Skill)**
- [ ] **Step 4: Criar modulo-1-4.html (Como o Claude Escolhe)**
- [ ] **Step 5: Criar modulo-1-5.html (Progressive Disclosure)**
- [ ] **Step 6: Criar modulo-1-6.html (Primeira Skill do Zero)**
- [ ] **Step 7: Verificar checklist em cada arquivo**
- [ ] **Step 8: Commit**

```bash
git add curso/trilha1/
git commit -m "feat: trilha1 módulos 1.1 a 1.6"
```

---

### Task 5: Trilha 2 — Index (Dicas Técnicas / Blue)

**Files:**
- Create: `curso/trilha2/index.html`

**Conteúdo:**
- Badge: TRILHA 2
- Título: 🔧 Dicas Técnicas
- Stats: 8 Módulos, 48+ Tópicos, ~4h, Intermediário
- Navegação Rápida: grid 2-3 colunas com 8 cards-âncora
- 8 Cards de Módulo com tópicos expansíveis:

**Módulo 2.1 — 🧊 Rode a Frio** (~25 min)
Tópicos: 1. O que é rodar a frio | 2. Por que prompts vagos revelam a verdade | 3. Como fazer o teste | 4. Interpretando o resultado | 5. O que fazer quando a skill errada dispara | 6. Checklist do teste frio

**Módulo 2.2 — 📏 Orçamento de Descrição** (~30 min)
Tópicos: 1. O limite de caracteres invisível | 2. O que o Claude realmente vê | 3. Gatilho sempre no início | 4. Escrevendo descrições enxutas | 5. Testando o truncamento | 6. Exemplos antes e depois

**Módulo 2.3 — 🎤 Faça a Skill Perguntar** (~35 min)
Tópicos: 1. O problema do loop morto | 2. O que é o Ask User Input Tool | 3. Quando pedir informações | 4. Quais perguntas fazem diferença | 5. Estruturando a entrevista | 6. Exemplo de skill com entrevista

**Módulo 2.4 — ✍️ Regras de Tom e Escrita** (~30 min)
Tópicos: 1. Por que skills de copy precisam de regras | 2. Anti-sycophancy | 3. Proibindo o m-dash | 4. Programando tonalidade | 5. Exemplos de regras de voz | 6. Onde colocar essas regras na skill

**Módulo 2.5 — ⭐ Nota da Experiência** (~25 min)
Tópicos: 1. A ideia do feedback loop | 2. Como pedir a nota | 3. A pergunta do porquê | 4. O que fazer com a nota | 5. Integrando na skill | 6. Exemplo de skill com rating

**Módulo 2.6 — 🔄 Feedback que Transforma** (~40 min)
Tópicos: 1. O que é reverse meta prompting | 2. Por que 90% não faz isso | 3. O prompt de reflexão | 4. Interpretando o diff da skill | 5. A melhoria de 1% por dia | 6. Exemplo de sessão de evolução

**Módulo 2.7 — 🔀 Primitiva Errada** (~30 min)
Tópicos: 1. Skill como muleta | 2. Skill vs Rule — quando cada um | 3. Skill vs Claude.md | 4. Skill vs CLI | 5. Skill vs Automação determinística | 6. O fluxo de decisão

**Módulo 2.8 — 🔍 Auditoria Séria** (~45 min)
Tópicos: 1. Por que auditar | 2. O agente claude-code-guide | 3. O prompt de auditoria | 4. Checklist estrutural | 5. O que fazer com os resultados | 6. Cadência de auditoria

- [ ] **Step 1: Criar curso/trilha2/index.html**
- [ ] **Step 2: Verificar checklist**
- [ ] **Step 3: Commit**

```bash
git add curso/trilha2/index.html
git commit -m "feat: trilha2 index"
```

---

### Task 6: Trilha 2 — Módulos 2.1 a 2.8

**Files:**
- Create: `curso/trilha2/modulo-2-1.html` até `curso/trilha2/modulo-2-8.html`

Cor da trilha: blue. Usar `text-blue-400`, `bg-blue-500/20`, `border-blue-500/30`, `from-blue-900/30`.

**Imagens a incorporar:**
- `modulo-2-2.html`: `../../doc/ChatGPT Image 13 de mai. de 2026, 23_53_33.png` (Truncamento)
- `modulo-2-3.html`: `../../doc/ChatGPT Image 13 de mai. de 2026, 23_53_39.png` (Loop morto)
- `modulo-2-8.html`: `../../doc/ChatGPT Image 13 de mai. de 2026, 23_59_00.png` (Playbook de poda)

- [ ] **Step 1: Criar modulo-2-1.html (Rode a Frio)**
- [ ] **Step 2: Criar modulo-2-2.html (Orçamento de Descrição)**
- [ ] **Step 3: Criar modulo-2-3.html (Faça a Skill Perguntar)**
- [ ] **Step 4: Criar modulo-2-4.html (Regras de Tom)**
- [ ] **Step 5: Criar modulo-2-5.html (Nota da Experiência)**
- [ ] **Step 6: Criar modulo-2-6.html (Feedback que Transforma)**
- [ ] **Step 7: Criar modulo-2-7.html (Primitiva Errada)**
- [ ] **Step 8: Criar modulo-2-8.html (Auditoria Séria)**
- [ ] **Step 9: Verificar checklist em cada arquivo**
- [ ] **Step 10: Commit**

```bash
git add curso/trilha2/
git commit -m "feat: trilha2 módulos 2.1 a 2.8"
```

---

### Task 7: Trilha 3 — Index (No Expert / Purple)

**Files:**
- Create: `curso/trilha3/index.html`

**Conteúdo:**
- Badge: TRILHA 3
- Título: 🧪 No Expert
- Stats: 6 Módulos, 36+ Tópicos, ~3h, Expert
- Navegação Rápida: grid 2 colunas com 6 cards-âncora
- 6 Cards de Módulo:

**Módulo 3.1 — 📋 Templates Prontos** (~40 min)
Tópicos: 1. Skill de entrevista universal | 2. Skill de reflexão pós-sessão | 3. Skill de consolidação | 4. Skill de auditoria rápida | 5. Como adaptar templates | 6. Onde guardar e versionar

**Módulo 3.2 — 💥 Prompts Canhão** (~35 min)
Tópicos: 1. O prompt de reverse meta prompting | 2. O prompt de auditoria com claude-code-guide | 3. O prompt de crítica estrutural | 4. O prompt de consolidação | 5. Combinando prompts em sequência | 6. Quando usar cada um

**Módulo 3.3 — 🤖 Sub-agentes para Testar** (~40 min)
Tópicos: 1. Por que sub-agentes são melhores que testes manuais | 2. Agente de UX friction | 3. Agente de auditoria estrutural | 4. Como ler os relatórios | 5. Priorizando high vs low impact | 6. Exemplo de sessão completa

**Módulo 3.4 — 🧹 Consolidação de Skills** (~35 min)
Tópicos: 1. Identificando sobreposições | 2. O Skill Creator 2.0 | 3. O processo de fusão | 4. Testando a skill consolidada | 5. Quando não consolidar | 6. Mantendo o histórico de versões

**Módulo 3.5 — 📊 Stack Lean de Skills** (~30 min)
Tópicos: 1. O inventário de skills | 2. Critérios de corte | 3. Quando deletar | 4. A regra do uso real | 5. Cadência de revisão | 6. Métricas de uma stack saudável

**Módulo 3.6 — 🔁 Skills que se Melhoram Sozinhas** (~45 min)
Tópicos: 1. O conceito de skill auto-iterativa | 2. Bake-in de reflexão | 3. Bake-in de avaliação | 4. O loop de melhoria contínua | 5. Limites e riscos | 6. Exemplo de skill completa com auto-iteração

- [ ] **Step 1: Criar curso/trilha3/index.html**
- [ ] **Step 2: Verificar checklist**
- [ ] **Step 3: Commit**

```bash
git add curso/trilha3/index.html
git commit -m "feat: trilha3 index"
```

---

### Task 8: Trilha 3 — Módulos 3.1 a 3.6

**Files:**
- Create: `curso/trilha3/modulo-3-1.html` até `curso/trilha3/modulo-3-6.html`

Cor da trilha: purple. Usar `text-purple-400`, `bg-purple-500/20`, `border-purple-500/30`, `from-purple-900/30`.

**Imagens a incorporar:**
- `modulo-3-5.html`: `../../doc/ChatGPT Image 13 de mai. de 2026, 23_59_00.png` (Playbook de poda)

- [ ] **Step 1: Criar modulo-3-1.html (Templates Prontos)**
- [ ] **Step 2: Criar modulo-3-2.html (Prompts Canhão)**
- [ ] **Step 3: Criar modulo-3-3.html (Sub-agentes para Testar)**
- [ ] **Step 4: Criar modulo-3-4.html (Consolidação de Skills)**
- [ ] **Step 5: Criar modulo-3-5.html (Stack Lean)**
- [ ] **Step 6: Criar modulo-3-6.html (Skills Auto-iterativas)**
- [ ] **Step 7: Verificar checklist em cada arquivo**
- [ ] **Step 8: Commit**

```bash
git add curso/trilha3/
git commit -m "feat: trilha3 módulos 3.1 a 3.6"
```

---

### Task 9: Deploy GitHub Pages e notificação

- [ ] **Step 1: Push para GitHub**

```bash
cd /home/nmaldaner/projetos/skills-premium
git add -A
git commit -m "feat: curso skills premium completo" --allow-empty
git branch -M main
git push -u origin main
```

- [ ] **Step 2: Habilitar GitHub Pages via API**

```bash
gh api repos/inematds/skills-premium/pages \
  --method POST \
  -f source.branch=main \
  -f source.path=/ 2>/dev/null || \
gh api repos/inematds/skills-premium/pages \
  --method PUT \
  -f source.branch=main \
  -f source.path=/
```

- [ ] **Step 3: Verificar URL do GitHub Pages**

```bash
gh api repos/inematds/skills-premium/pages | python3 -c "import sys,json; p=json.load(sys.stdin); print(p.get('html_url',''))"
```

- [ ] **Step 4: Enviar notificação via openpcbot**

```bash
/home/nmaldaner/projetos/openpcbot/scripts/notify.sh "⚡ <b>Skills Premium publicado!</b>

✅ 24 páginas criadas
🎯 3 trilhas: Fundamentos, Dicas Técnicas, No Expert
📦 20 módulos no total

🔗 GitHub Pages: https://inematds.github.io/skills-premium"
```
