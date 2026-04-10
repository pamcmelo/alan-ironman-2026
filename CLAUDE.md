# Alan — Ironman 70.3 Cozumel — Dashboard

Dashboard interativo de treino e nutrição para a preparação do Alan para o Ironman 70.3 Cozumel.

## O que é o projeto

Aplicação web (HTML/CSS/JS puro) sem backend. Duas abas principais:
- **Alimentação diária** — seleciona tipo de treino do dia e exibe metas calóricas + macros + distribuição de refeições
- **Treinamento** — plano de 25 semanas com marcação de treinos concluídos, countdown para a prova, e filtro por fase

## Estrutura dos arquivos

| Arquivo | Conteúdo |
|---|---|
| `index.html` | Estrutura HTML completa (~130 linhas) |
| `style.css` | Todo o CSS — layout, cores, dark mode, responsivo |
| `script.js` | Dados de treino e nutrição + toda a lógica JavaScript |

**Onde ficam as coisas importantes em `script.js`:**
- Dados de nutrição por tipo de treino → objeto `DAYS` no início do arquivo
- Dados do plano de treino (25 semanas) → array `WEEKS`
- Integração com Google Sheets → função `toggleDone` (usa GET para evitar CORS)
- Lógica de countdown e progresso → função `renderTraining`

## Como testar localmente

```bash
open index.html
```

Abre direto no browser. A integração com Google Sheets funciona normalmente.

## Como fazer deploy

Push para `main` → GitHub Pages atualiza automaticamente em `pamcmelo.github.io/alan-ironman-2026`.

## Informações do projeto

- **Prova:** IRONMAN 70.3 Cozumel — 20 de setembro de 2026
- **Perfil do atleta:** Alan, 62 kg, 33 kg de massa magra (referência para cálculos de nutrição)
- **Fases de treino:** 7 fases — Base terrestre → Bacalar → Natação+build → Volume+bricks → Pico → Taper → Prova
- **Idioma:** Português brasileiro — manter assim em todos os ajustes

## Regras para ajustes

- Sempre testar abrindo `index.html` no browser após qualquer mudança
- Nunca alterar cálculos de macros sem confirmar com a Pam primeiro
- Alertas médicos (seção "Pontos críticos") — não remover sem confirmação
- A integração com Google Sheets usa GET (não POST) — manter assim para evitar bloqueio por CORS
