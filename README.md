# Programação · Convenção de Polos 2026

Tela de programação do evento para TV (16:9), alimentada por uma planilha Google Sheets.

**Endereço:** https://duzaoatos-commits.github.io/programacao-convencao-2026/

## Como funciona

- Lê a aba `programacao` da planilha a cada 60 s (a planilha precisa estar compartilhada como "qualquer pessoa com o link: leitor").
- Ciclo: Agora/A seguir → próximas 4 → Agora/A seguir → próximas 4 → … com a vinheta da logo a cada volta (no máximo a cada 5 min).
- Atividades somem quando terminam; o dia é escolhido pela data do computador.
- Sem internet, continua com os últimos dados carregados.

## Testes pela URL

| Parâmetro | Exemplo | O que faz |
|---|---|---|
| `agora` | `?agora=10:35` | simula o horário |
| `data` | `?data=2026-11-04` | simula o dia |
| `vel` | `?vel=30` | acelera o relógio |
| `dia` | `?dia=2` | fixa a página num dia |
| `vinheta` | `?vinheta=0` | desliga a vinheta |
| `planilha` | `?planilha=ID` | usa outra planilha |

Os tempos de cada tela e o ID da planilha ficam no bloco `CONFIG` no início do script em `index.html`.
