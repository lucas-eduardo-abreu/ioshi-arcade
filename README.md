# 🍣 Ioshi · Arcade de Mesa

Coleção de mini-jogos casuais pensada pra rodar em **tablets de mesa de sushi bar** — aquele intervalo entre pedidos em que a galera fica parada esperando a esteira chegar. Identidade visual do [Ioshi Sushi](https://www.ioshisushi.com.br/).

Cada jogo é um arquivo HTML único, zero dependências (só duas fontes do Google Fonts), *touch-first*, sem backend. `index.html` é o hub que lista todos os jogos; cada um tem um botão **← Menu** pra voltar.

## Jogos

| | Jogo | Arquivo | Jogadores |
|---|------|---------|:---:|
| 🍣 | **Festival Rush** — pratos correm na esteira, toque só no pedido da mesa antes que passe | `ioshi-festival-rush.html` | 1–2 |
| 🔪 | **Corte Perfeito** — toque no instante exato em que a faca cruza a zona dourada | `ioshi-corte-perfeito.html` | 1 |
| 🧠 | **Memória** — vire as cartas e encontre os pares de sushi | `ioshi-memoria.html` | 1 |
| 📝 | **Monte o Pedido** — memorize a ordem e remonte tocando nos ingredientes certos | `ioshi-monte-pedido.html` | 1 |
| 🐱 | **Pega o Gato** — toque nos gatos antes que roubem o sushi do balcão | `ioshi-pega-gato.html` | 1 |
| 🐟 | **Adivinhe o Peixe** — quiz de 10 perguntas sobre o mundo do sushi | `ioshi-adivinhe-peixe.html` | 1 |
| ⚔️ | **Duelo** — tablet no meio da mesa, reação mais rápida vence | `ioshi-duelo.html` | 2 |
| 🎰 | **Gashapon da Sorte** — gire a cápsula e descubra o mimo do dia | `ioshi-gashapon.html` | 1 |
| 🍱 | **Qual Sushi Você É?** — quiz de personalidade, compartilhável | `ioshi-qual-sushi.html` | 1 |

### Festival Rush em detalhe

Escolha **1 Jogador** ou **2 Jogadores** (esteira dividida ao meio, cada um com seu próprio pedido e placar). O "pedido da mesa" aparece no topo de cada esteira. Os pratos rolam — toque **só** nos que batem com o pedido. Acertos em sequência sobem o combo (até x5), o pedido troca sozinho, e o **wasabi é armadilha** (−3s, afeta os dois jogadores no modo dupla). São 60 segundos e a esteira acelera com o tempo.

Todo jogo sorteia um **prato do dia** (★): acertar o pedido quando ele coincidir com o prato do dia rende +50% de pontos. O recorde persiste entre sessões via `localStorage`.

| Ação | Efeito |
|------|--------|
| Tocar no prato do pedido | +pontos (× multiplicador do combo) |
| Tocar no pedido quando é o prato do dia | +pontos ×1.5 |
| Tocar em prato errado | combo zera, −1s |
| Tocar no wasabi 🟢 | combo zera, −3s |
| Deixar o pedido passar | combo zera |

## Rodar localmente

É tudo HTML estático — basta abrir `index.html` no navegador. Ou servir:

```
python -m http.server 8000
```

E acessar `http://localhost:8000`.

## Publicar no GitHub Pages

Como o hub está em `index.html` na raiz, é só ir em **Settings → Pages**, escolher a branch `main` / pasta `/root`, e o arcade fica no ar em `https://<usuario>.github.io/esteira-rush/`.

## Stack

- HTML + CSS + JavaScript puro (vanilla), sem build
- Loop com `requestAnimationFrame` e delta time
- Áudio via Web Audio API (destrava após o primeiro toque, com botão de mudo)
- Fontes: Zen Maru Gothic + M PLUS Rounded 1c
- Recorde persistido via `localStorage` (Festival Rush)

## Licença

MIT — veja [LICENSE](LICENSE).
