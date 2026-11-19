# Protótipo de RA na paragem (G4, VDI, M2)

Aponta-se a câmara ao cartaz `marcador_paragem.png` (paragem João XXI, 31 de Janeiro I) e aparece por cima o painel com os próximos autocarros, a hora estimada e o atraso. Os dados vêm da simulação SUMO do centro de Braga (07h-10h, dia normal e com obras na Av. da Liberdade). Na barra de baixo escolhe-se o cenário e a "hora atual".

Tecnologia: A-Frame 1.5.0 + MindAR 1.2.5 (rastreio de imagem), tudo local na pasta `lib/` (não precisa de internet). O marcador foi compilado para `marcador_paragem.mind`.

## Opção 1: no PC, com a webcam (o mais simples para a apresentação)

```
cd RA_paragem
python -m http.server 8000
```

Abre http://localhost:8000 no Chrome ou no Edge e deixa usar a câmara. Mostra o marcador à webcam, impresso ou aberto no ecrã do telemóvel. Se a câmara falhar, o botão "Ver sem câmara" mostra o mesmo painel em 2D.

## Opção 2: no telemóvel (precisa de HTTPS)

O telemóvel só dá acesso à câmara em páginas HTTPS. A forma mais rápida é o GitHub Pages:

1. Cria um repositório público no GitHub (ex.: `g4-ra-paragem`) e carrega o conteúdo desta pasta (com a pasta `lib/`).
2. Settings → Pages → Source: "Deploy from a branch", branch `main`, pasta `/ (root)` → Save.
3. Passado um minuto, abre `https://<utilizador>.github.io/g4-ra-paragem/` no telemóvel e aponta ao marcador (impresso ou no ecrã do PC).

## Ficheiros

- `index.html`: a página de RA
- `marcador_paragem.png` / `.mind`: o cartaz e o alvo compilado
- `dados_paragem.json`: 51 passagens por cenário nesta paragem, das 7h às 10h (saída do SUMO no formato do contrato)
- `captura_teste.png`: teste feito com câmara simulada (alvo encontrado)
