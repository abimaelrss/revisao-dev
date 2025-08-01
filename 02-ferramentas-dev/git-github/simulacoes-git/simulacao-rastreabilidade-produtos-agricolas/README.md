
# 🔍 Simulação Git Aplicada: Sistema de Rastreabilidade de Produtos Agrícolas

Este projeto simula o uso do Git para documentar e versionar o ciclo completo de rastreabilidade de um lote de produtos agrícolas, desde o campo até a entrega ao consumidor.

## 📁 Estrutura do Dossiê de Rastreabilidade

```
rastreabilidade-lote-001/
├── 01-origem-producao/
│   ├── talhao-origem.md
│   ├── data-plantio-colheita.md
│   └── insumos-utilizados.md
├── 02-processamento-embalagem/
│   ├── data-processamento.md
│   ├── lote-embalagem.md
│   └── condicoes-armazenamento.md
├── 03-transporte-distribuicao/
│   ├── data-envio.md
│   ├── veiculo-responsavel.md
│   └── destino-final.md
├── 04-controles-qualidade/
│   ├── inspecao-final-lote.md
│   └── certificacoes-organicas.md
├── incidentes-observacoes/
│   ├── ocorrencias-campo.md
│   └── feedback-consumidor.md
└── README.md
```

## 🔄 Fluxo de Versionamento com Git

- Branch principal: `lote-001` – linha do tempo oficial do dossiê.
- Branches auxiliares:
  - `desenvolvimento/processamento`: documentação do beneficiamento e embalagem.
  - `desenvolvimento/certificacoes`: documentação da certificação orgânica.
- Técnicas aplicadas:
  - `git commit`, `git merge`, `git rebase`, `git reset --soft`, `git commit --amend`.

## 🧪 Funcionalidades Simuladas

- Criação e versionamento de arquivos de produção, processamento, transporte e controle de qualidade.
- Correções com `amend`, descarte de registros com `reset --soft`, rebase de desenvolvimento com histórico linear.
- Integração de feedbacks e ocorrências.
- Uso de branches para isolar e integrar mudanças no dossiê.

## ✅ Conclusão

A rastreabilidade agrícola exige organização, precisão e integridade de dados. O uso do Git neste contexto permite:

- **Rastreamento completo e auditável.**
- **Organização por fases.**
- **Transparência e confiabilidade.**
- **Facilidade para certificações e auditorias.**

---

## 🛠️ Como Reproduzir a Simulação

Para reproduzir este projeto e praticar os comandos, siga as instruções detalhadas no arquivo `roteiro.md` anexo.

---

## ✨ Comandos Utilizados (Resumo)

- `mkdir`
- `cd`
- `git init`
- `git config`
- `git status`
- `git add`
- `git commit -m`
- `git switch -c`
- `git switch`
- `git merge`
- `git branch -d`
- `git commit --amend -m`
- `git reset --soft`
- `git restore`
- `git reset --hard`
- `git rebase`
- `git log --oneline --all --graph`

---

**Simulação desenvolvida para fins educacionais no uso do Git em contextos do agronegócio.**
