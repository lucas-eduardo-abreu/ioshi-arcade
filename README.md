# 🍣 Ioshi · Festival Rush

Jogo casual de esteira (*kaiten*) pensado pra rodar em **tablets de mesa de sushi bar** — aquele intervalo entre pedidos em que a galera fica parada esperando a esteira chegar. Identidade visual do [Ioshi Sushi](https://www.ioshisushi.com.br/).

Arquivo único, zero dependências (só duas fontes do Google Fonts), *touch-first*. Roda numa PWA/navegador travado sem backend.

## Como jogar

Escolha **1 Jogador** ou **2 Jogadores** (esteira dividida ao meio, cada um com seu próprio pedido e placar). O "pedido da mesa" aparece no topo de cada esteira. Os pratos rolam — toque **só** nos que batem com o pedido. Acertos em sequência sobem o combo (até x5), o pedido troca sozinho, e o **wasabi é armadilha** (−3s, afeta os dois jogadores no modo dupla). São 60 segundos e a esteira acelera com o tempo.

Todo jogo sorteia um **prato do dia** (★): acertar o pedido quando ele coincidir com o prato do dia rende +50% de pontos.

| Ação | Efeito |
|------|--------|
| Tocar no prato do pedido | +pontos (× multiplicador do combo) |
| Tocar no pedido quando é o prato do dia | +pontos ×1.5 |
| Tocar em prato errado | combo zera, −1s |
| Tocar no wasabi 🟢 | combo zera, −3s |
| Deixar o pedido passar | combo zera |

## Rodar localmente

É um HTML estático — basta abrir `index.html` no navegador. Ou servir:

```
python -m http.server 8000
```

E acessar `http://localhost:8000`.

## Publicar no GitHub Pages

Como o jogo está em `index.html` na raiz, é só ir em **Settings → Pages**, escolher a branch `main` / pasta `/root`, e o jogo fica no ar em `https://<usuario>.github.io/esteira-rush/`.

## Stack

- HTML + CSS + JavaScript puro (vanilla), sem build
- Loop com `requestAnimationFrame` e delta time
- Áudio via Web Audio API (destrava após o primeiro toque, com botão de mudo)
- Fontes: Zen Maru Gothic + M PLUS Rounded 1c
- Recorde persistido via `localStorage`

## Roadmap

- [x] Persistência do recorde (`localStorage`)
- [x] Modo 2 jogadores dividindo a esteira (disputa de mesa, sem backend)
- [ ] Trocar os emojis por arte do próprio cardápio (menu jogável)
- [x] "Prato do dia" com bônus de pontuação (+50%)

## Licença

MIT — veja [LICENSE](LICENSE).
