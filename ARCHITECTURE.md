# Arquitetura do Sistema

## Visão Geral

O Núcleo Tático é um ecossistema digital composto por 4 pilares principais:

```
┌─────────────────────────────────────────────────────────┐
│              NÚCLEO TÁTICO v2.0 (2026)                  │
├─────────────────────────────────────────────────────────┤
│  1. PLATAFORMA DE CURSOS     2. INTELIGÊNCIA ARTIFICIAL  │
│     • 24+ cursos                 • Agente principal     │
│     • 10 categorias              • 114 skills            │
│     • Certificações              • Pipeline 7 camadas    │
│                                                          │
│  3. MCP ACADÊMICO            4. MONITORAMENTO            │
│     • PostgreSQL                 • Inteligência tático- │
│     • arXiv API                    médica               │
│     • Pipeline ABNT              • Concursos/Editais   │
│     • Dashboard                  • Legislação            │
└─────────────────────────────────────────────────────────┘
```

## 1. Plataforma de Cursos

### Categorias (10 nichos)

| # | Categoria | Cursos | Código |
|---|-----------|--------|--------|
| 01 | Fundamentos | 4 | NT-FUN |
| 02 | Core | 4 | NT-COR |
| 03 | Tático-Médico | 5 | NT-TAT |
| 04 | Escolas | 4 | NT-ESC |
| 05 | Esportes | 3 | NT-ESP |
| 06 | Outdoor | 2 | NT-OUT |
| 07 | Industrial | 2 | NT-IND |
| 08 | Eventos | 2 | NT-EVT |
| 09 | Emergência | 2 | NT-EME |
| 10 | Especializados | 1 | NT-ESP |

### Pipeline de Produção

```
Pesquisa → Validação → Produção → Revisão → Publicação → Monetização → Escala
```

## 2. Inteligência Artificial

### Agente Principal (Kimi Claw)

- **Modelo:** Kimi K2.5 (kimi-coding/k2p5)
- **Runtime:** OpenClaw (agente principal)
- **Workspace:** `/root/.openclaw/workspace/`
- **Memória:** MEMORY.md + daily logs
- **Skills:** 114 ativas (63 oficiais + 51 extras)

### Pipeline de Qualidade IA (7 camadas)

```
Input do Usuário
       ↓
[1] Security Filter (Rebuff)
       ↓
[2] RAG - Haystack + Sentence Transformers
       ↓
[3] LLM - Kimi K2.5
       ↓
[4] Structure Validation - Guardrails + Pydantic
       ↓
[5] Hallucination Check - RAGAS
       ↓
[6] Quality Evaluation - DeepEval
       ↓
[7] Response Output
```

### Thresholds Numéricos

| Métrica | Threshold | Ferramenta |
|---------|-----------|------------|
| Faithfulness | ≥ 0.80 | RAGAS |
| Answer Relevancy | ≥ 0.70 | RAGAS |
| Contextual Precision | ≥ 0.75 | RAGAS |
| G-Eval | ≥ 0.70 | DeepEval |
| Hallucination | < 0.30 | DeepEval |

## 3. MCP Acadêmico Autônomo

### Stack Tecnológica

| Componente | Tecnologia | Status |
|------------|-----------|--------|
| Banco de dados | PostgreSQL 16 | ✅ OK |
| Schema | 5 tabelas (projetos, referencias, secoes, notas, tarefas) | ✅ OK |
| API de busca | arXiv API | ✅ OK |
| Busca secundária | Semantic Scholar (API key gratuita) | ⚠️ Pendente |
| Busca primária | PubMed E-utilities | ❌ Bloqueado IP China |
| Framework | FastAPI + SQLAlchemy | ✅ OK |
| Ambiente | Python venv (venv-mcp) | ✅ OK |

### Pipeline Bibliográfico

```
Ideia de Tema
      ↓
Busca arXiv → Metadados → PDF → Texto
      ↓
Formatação ABNT (NBR 6023:2018)
      ↓
Salvamento PostgreSQL
      ↓
Indexação semântica (pgvector — pendente)
      ↓
Escrita de rascunhos (agente — pendente)
```

## 4. Monitoramento Inteligência

### Fontes Prioritárias

| Prioridade | Fonte | Frequência |
|-----------|-------|------------|
| 🔴 Crítica | CoTCCC, C-TECC, AHA, K9-TECC | 2x/dia |
| 🟡 Alta | Stop The Bleed, NAEMT, ACS-COT | Semanal |
| 🟢 Média | PubMed, medRxiv, ILCOR | Mensal |

### Relatório Inteligência Diária (3 edições)

| Edição | Horário | Foco |
|--------|---------|------|
| Matinal | 07:00 BRT | Notícias da madrugada, oportunidades |
| Meio-dia | 13:00 BRT | Atualizações mercado, novos editais |
| Noturna | 20:00 BRT | Resumo do dia, preparar amanhã |

## Infraestrutura

### Servidor

- **VPS:** Alibaba Cloud (Asia/Shanghai)
- **OS:** Linux 6.8.0-90-generic
- **Node.js:** v22.22.0
- **Python:** 3.12
- **PostgreSQL:** 16

### Canais de Comunicação

| Canal | Uso | Status |
|-------|-----|--------|
| Telegram | Principal (chat direto) | ✅ Ativo |
| Feishu | Documentos colaborativos | ✅ Ativo |
| WhatsApp | Chatbot leads (futuro) | ⚠️ Planejado |
| Email | Notificações formais | ✅ Configurado |

### Backup e Segurança

- **Git:** Repositório local (falta push GitHub)
- **Google Drive:** rclone configurado (falta autenticação usuário)
- **Regras:** Sem credenciais no repo, trash > rm

## Roadmap Técnico 2026

### Q2 (Abr-Jun)
- [ ] Integrar arXiv no agente bibliográfico
- [ ] Instalar pgvector no PostgreSQL
- [ ] Criar dashboard Next.js básico
- [ ] Configurar envio automático Telegram

### Q3 (Jul-Set)
- [ ] Agente CrewAI com múltiplos agentes
- [ ] Busca semântica com embeddings
- [ ] Landing page SaaS Acadêmico
- [ ] 30 cursos catalogados

### Q4 (Out-Dez)
- [ ] Pipeline completo: ideia → publicação
- [ ] Dashboard admin completo
- [ ] Sistema de afiliados
- [ ] Chatbot WhatsApp

---

**Documentação técnica mantida por:** Kimi Claw 🤖  
**Última atualização:** 2026-05-02  
**Versão:** v2.0.0

**NÃO NEGOCIE COM SUA MENTE!** 🎖️
