# 🔧 SCRIPTS DE AUTOMAÇÃO

Scripts Python/Node.js para automação interna do Núcleo Tático.

---

## 📂 Estrutura

```
scripts/
├── geracao/           # Geração de conteúdo
│   ├── gerar_questoes.py
│   ├── gerar_slides.py
│   └── gerar_apostila.py
├── conversao/         # Conversão de formatos
│   ├── md_para_docx.py
│   ├── md_para_pdf.py
│   └── abnt_formatter.py
├── inteligencia/      # Monitoramento e relatórios
│   ├── monitor_cotccc.py
│   ├── monitor_tecc.py
│   └── relatorio_diario.py
├── utilidades/        # Ferramentas diversas
│   ├── validar_abnt.py
│   ├── contar_palavras.py
│   └── verificar_links.py
└── README.md          # Este arquivo
```

---

## 🚀 Scripts Principais

### 1. Geração de Questões (CrewAI)
**Arquivo:** `geracao/gerar_questoes.py`  
**Função:** Gera questões de concurso a partir de editais  
**Entrada:** PDF do edital + tema  
**Saída:** JSON com 50 questões formatadas  
**Uso:**
```bash
python3 gerar_questoes.py --edital edital_pmerj_2026.pdf --tema "Direito Constitucional"
```

### 2. Conversão Markdown → DOCX
**Arquivo:** `conversao/md_para_docx.py`  
**Função:** Converte apostila Markdown para DOCX editável  
**Entrada:** `CURSO_COMPLETO_NT-XXX-XXX.md`  
**Saída:** `CURSO_COMPLETO_NT-XXX-XXX.docx`  
**Uso:**
```bash
python3 md_para_docx.py --input NT-ESC-001.md --output NT-ESC-001.docx --template template_NT_master.docx
```

### 3. Monitoramento CoTCCC
**Arquivo:** `inteligencia/monitor_cotccc.py`  
**Função:** Verifica novos Change Proposals no CoTCCC  
**Frequência:** 2x/dia (cron job)  
**Saída:** Alerta para Telegram se houver novidade  
**Uso:**
```bash
python3 monitor_cotccc.py --notify telegram
```

### 4. Relatório Inteligência Diária
**Arquivo:** `inteligencia/relatorio_diario.py`  
**Função:** Compila notícias dos 4 nichos monitorados  
**Frequência:** 3x/dia (07:00, 13:00, 20:00 BRT)  
**Saída:** Markdown formatado + envio Telegram  
**Uso:**
```bash
python3 relatorio_diario.py --edicao matinal
```

---

## 🛠️ Instalação

```bash
# Clonar repo
git clone https://github.com/nucleotatico/nt-repo-github.git
cd nt-repo-github/scripts

# Instalar dependências
pip install -r requirements.txt

# Configurar variáveis de ambiente
cp .env.example .env
nano .env
```

---

## ⚙️ Variáveis de Ambiente

```bash
# APIs
OPENAI_API_KEY=sk-...
ANTHROPIC_API_KEY=sk-...
KIMI_API_KEY=...

# Banco de dados
DATABASE_URL=postgresql://nt_academico:senha@localhost:5432/academia_nt

# Telegram
TELEGRAM_BOT_TOKEN=...
TELEGRAM_CHAT_ID=...

# Supabase
SUPABASE_URL=https://...supabase.co
SUPABASE_KEY=...

# Hotmart
HOTMARMT_API_KEY=...
```

---

## 📋 Requisitos

```
Python >= 3.10
Node.js >= 18
PostgreSQL >= 16
Redis >= 7
```

---

## 📝 Contribuindo

1. Crie uma pasta nova se necessário
2. Adicione docstring ao script
3. Inclua exemplo de uso
4. Teste antes de commitar

---

**NÚCLEO TÁTICO** — *"NÃO NEGOCIE COM SUA MENTE!"*
