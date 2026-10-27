# Programação · Convenção de Polos 2026

Tela de programação do evento para TV (16:9), alimentada por uma planilha Google Sheets.

**TV:** https://duzaoatos-commits.github.io/programacao-convencao-2026/

**Celular:** https://duzaoatos-commits.github.io/programacao-convencao-2026/celular.html (lista completa por dia, com "Agora" em destaque; a TV mostra um QR code para ela)

**Controle do operador:** https://duzaoatos-commits.github.io/programacao-convencao-2026/controle.html

## Controle do operador

A TV e o controle conversam de dois jeitos:

- **Mesmo computador:** direto pelo navegador, sem internet (BroadcastChannel).
- **Celular ou outro aparelho:** pelo serviço gratuito ntfy.sh, num canal privado. Abra a TV com `?canal=CÓDIGO` e o controle com `controle.html?canal=CÓDIGO` (o mesmo código nos dois). O código fica guardado no navegador depois da primeira vez. Não publique o código: quem tiver ele consegue comandar a TV.

Funções:

- **Finalizar:** tira a atividade da TV na hora; a próxima vira o destaque como "A seguir". Dá para desfazer.
- **Chamar intro:** vinheta da logo da convenção seguida da abertura animada da atividade (título, palestrantes, fotos e horário), com música. O som sai da aba da TV; clique uma vez na tela da TV ao montar para o navegador liberar o áudio (o controle mostra se o som está liberado).
- **Música:** `musica-intro.mp3` na raiz do site (troque o arquivo para mudar a trilha; sem ele, toca uma trilha gerada pela página).
- **Atalhos na janela da TV:** `I` intro da próxima · `F` finalizar a atual · `Z` desfazer · `Esc` parar a intro.
- A finalização vale só para a TV; a página do celular do público continua seguindo os horários da planilha.

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
