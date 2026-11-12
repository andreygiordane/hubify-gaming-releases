# Voz e transmissão

[← Voltar à documentação](../README.md#documentação)

## Salas de voz

Toque em um canal de **voz** para entrar. Na lista aparece quem está na sala (com o jogo de cada pessoa, quando permitido) e, dentro da sala, você vê os participantes e usa os controles:

| Controle | O que faz |
|---|---|
| **Microfone** | Liga ou silencia o seu microfone. |
| **Fones** | Silencia o áudio que você ouve. |
| **Transmitir** | Compartilha a janela do jogo (veja [abaixo](#transmitir-o-jogo)). |
| **Ajustes** | Escolha de microfone, saída de áudio e opções de voz. |
| **Sair** | Deixa a sala. |

Cada sala de voz tem um **chat próprio**: o ícone de balão abre as mensagens daquela sala.

### Como o áudio trafega

A voz usa **WebRTC**: o áudio vai **direto entre os aparelhos**, com criptografia padrão do WebRTC. O servidor faz só a **sinalização** (apresenta os aparelhos uns aos outros) e confere quem pode entrar. Quando a rede de alguém impede a conexão direta, um servidor de retransmissão (**TURN**) repassa o tráfego **já cifrado**, sem guardá-lo.

Consequência prática: salas de voz funcionam bem para **grupos de squad**. Salas muito grandes exigem mais do computador e da internet de cada pessoa, porque cada participante se conecta aos demais.

### Apertar para falar (PTT)

- **App do Windows:** tecla **global**, funciona mesmo com o jogo em primeiro plano. Só a tecla que você escolheu é monitorada (nada do que você digita é lido).
- **Navegador e Android:** funciona com o app em foco.

Configure em **Configurações → Voz e vídeo → Apertar para falar**:

1. **Ligue** o recurso.
2. Toque em **Gravar atalho** e aperte a tecla desejada (**Esc** cancela; o **X** remove o atalho).
3. Ajuste o **atraso após soltar** (0 a 2000 ms) para o microfone ficar aberto por mais um instante e não cortar o fim da frase.

Sem atalho definido, com o recurso ligado, o microfone fica fechado.

### Dicas de qualidade

- Use **fones**: evita eco.
- Prefira **cabo de rede** ou Wi-Fi de 5 GHz.
- Em **Voz e vídeo**, confira o microfone certo e use o medidor de nível para testar.
- Se a voz falhar só em redes específicas (por exemplo, 4G de algumas operadoras), veja [Solução de problemas](SOLUCAO-DE-PROBLEMAS.md#a-voz-não-conecta-ou-fica-picotando).

## Palco

O **Palco** é uma sala para **poucos oradores e muitos ouvintes**: eventos, treinos, anúncios.

1. Ouvintes entram mudos. Quem quer falar usa **Levantar a mão**.
2. Quem gerencia o palco **chama ao palco** a pessoa escolhida.
3. Só quem está no palco é ouvido pelos demais.

## Transmitir o jogo

Compartilhe a janela do jogo com o squad em até **1080p a 60 FPS**.

| Onde | Como funciona |
|---|---|
| **App do Windows** | Só a **janela** é oferecida (nunca a tela inteira). Se o app reconheceu o jogo aberto, a janela dele já vem **selecionada**. |
| **Navegador** | O navegador pergunta o que compartilhar; a opção de tela inteira é escondida onde o navegador permite. |
| **Android** | **Não disponível** (limitação do sistema). Dá para **assistir** transmissões. |
| **Celular (assistindo)** | Tela cheia com controles ao toque; o vídeo ocupa 100% da tela e tenta travar em paisagem. |

**Limites conhecidos**

- No Windows, o **áudio do compartilhamento** é o do sistema inteiro (e não só o do jogo).
- Jogos em **tela cheia exclusiva** podem aparecer pretos na transmissão: use o modo **janela sem borda**.
- A qualidade se ajusta sozinha à conexão (por exemplo, menor quando a rota passa pelo servidor de retransmissão).

### Pedido de transmissão

Quem quer assistir pode **pedir** que alguém transmita. O pedido é um aviso **temporário**, mostrado ao streamer; ele **não** vai para o chat.

## Status automático (app do Windows)

Opcional e com permissão. O app lê **apenas** o nome do programa em execução e o título/artista que o Windows já mostra no controle de mídia: nada é lido de dentro do jogo.

- **Jogo:** reconhece Steam, Epic, GOG e pastas de outras lojas e mostra a **capa** ao lado do seu nome. Nome oficial e capa vêm da base **IGDB** (enviamos só o nome do jogo).
- **Música:** reconhece Spotify, YouTube, YouTube Music, Apple Music, Deezer, SoundCloud e outros. Sites desconhecidos são ignorados.
- A música só aparece se **não houver jogo** detectado.

Você liga e desliga cada um em **Configurações**.
