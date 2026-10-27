# Programação · Convenção de Polos 2026

Tela de programação do evento para TV (16:9), alimentada por uma planilha Google Sheets.

**TV:** https://duzaoatos-commits.github.io/programacao-convencao-2026/

**Celular:** https://duzaoatos-commits.github.io/programacao-convencao-2026/celular.html (lista completa por dia, com "Agora" em destaque; a TV mostra um QR code para ela)

**Controle do operador:** https://duzaoatos-commits.github.io/programacao-convencao-2026/controle.html

## Controle do operador

Abra a TV e o controle no mesmo navegador do mesmo computador (TV em tela cheia no telão, controle no monitor do operador). Os dois conversam direto, sem servidor.

- **Finalizar:** tira a atividade da TV na hora; a próxima vira o destaque como "A seguir". Dá para desfazer.
- **Chamar intro:** abertura animada da atividade no telão (título, palestrantes, fotos e horário) com música. O som sai do computador do operador. Ao terminar, a TV volta para o ciclo normal.
- **Música:** coloque um arquivo `musica-intro.mp3` na raiz do site para usar uma trilha própria; sem ele, toca uma trilha gerada pela página.
- **Atalhos na janela da TV:** `I` intro da próxima · `F` finalizar a atual · `Z` desfazer · `Esc` parar a intro.
- A finalização vale só para a TV daquele computador; a página do celular continua seguindo os horários da planilha.

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
