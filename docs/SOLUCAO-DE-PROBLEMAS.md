# Solução de problemas

[← Voltar à documentação](../README.md#documentação)

Antes de tudo, tente o básico: **recarregue** a página (ou feche e abra o app) e confira se você está na **versão mais recente** ([Atualizações](ATUALIZACOES.md)).

## Entrar e cadastrar

**"Usuário ou senha incorretos."**
Confira maiúsculas/minúsculas e se o teclado não está com Caps Lock. Você pode entrar com **usuário ou e-mail**. Depois de várias tentativas erradas o acesso é **bloqueado por um tempo** (espere e tente de novo).

**"Muitas tentativas. Aguarde..."**
É a proteção contra tentativa e erro. Espere o tempo indicado (de 1 a 15 minutos, conforme o caso).

**Pede um "código de verificação" ao entrar.**
Sua conta tem a **verificação em duas etapas**. Digite o código de 6 dígitos do app autenticador ou um **código de recuperação**.

**"Código incorreto" na 2FA.**
O relógio do celular precisa estar **certo** (ative a hora automática). Cada código vale uma vez: espere o próximo.

**O link de convite não funciona.**
Pode ter expirado, atingido o limite de usos ou sido substituído por um novo. Peça outro link a quem convidou.

**O código de e-mail não chega.**
Veja o spam, confirme o endereço e use **Reenviar código** depois do intervalo indicado.

## Mensagens e criptografia

**Vejo "🔒 Mensagem protegida" em vez do texto.**
Este aparelho ainda não tem a chave. Toque em **Desbloquear** e digite a **senha de mensagens**.

**"Senha de mensagens incorreta."**
É a senha que **você criou ao ativar a criptografia**, não a senha da conta. Se esqueceu, use **Esqueci a senha** para redefinir (as mensagens protegidas antigas não poderão ser lidas).

**O cadeado está amarelo / "O código de segurança mudou".**
A outra pessoa redefiniu a criptografia ou trocou de conta (ou, raramente, há alguém no meio). Compare o **número de segurança** com ela por outro meio e toque em **Conferi, está igual**.

**A mensagem não envia ("Não enviei em texto aberto").**
O app **recusa rebaixar** uma conversa protegida para texto aberto. Desbloqueie suas mensagens ou aguarde a chave da outra pessoa ficar disponível; a mensagem fica na fila e é reenviada.

**Uma conversa tem cadeado aberto.**
A outra pessoa ainda não ativou a criptografia de ponta a ponta. Quando ela ativar, a proteção começa sozinha.

## Voz e transmissão

**Não ouço ninguém / ninguém me ouve.**
1. Permita o **microfone** quando o navegador ou o app pedir (e confira nas permissões do site/sistema).
2. Em **Configurações → Voz e vídeo**, confirme o microfone e a saída de áudio e use o medidor de nível.
3. Veja se você não está **silenciado** (microfone ou fones cortados na barra da sala).

### A voz não conecta ou fica picotando

- Troque de rede (Wi-Fi ↔ 4G/5G) para testar: algumas redes (CGNAT, firewalls corporativos) bloqueiam conexões diretas. O servidor oferece uma rota de **retransmissão (TURN)** para esses casos, mas ela pode adicionar atraso.
- Use **fones** (evita eco) e feche programas que usam muita internet.
- Salas **muito grandes** pesam no computador e na conexão de cada participante.

**A transmissão sai preta.**
Jogos em **tela cheia exclusiva** podem não ser capturados: use o modo **janela sem borda**. No navegador, escolha **Janela** em vez de **Tela inteira**.

**Não consigo transmitir no Android.**
Compartilhar tela não está disponível no Android (limitação do sistema). Você pode assistir.

**Apertar para falar não funciona no jogo.**
A tecla **global** só existe no **app do Windows** (no navegador e no Android funciona com o app em foco). Confira a tecla em **Voz e vídeo**.

## Instalar e atualizar

**O Windows bloqueou o instalador (SmartScreen).**
Clique em **Mais informações → Executar assim mesmo**. Antes, [confira o SHA-256](INSTALACAO.md#verificar-o-arquivo-sha-256).

**O Android não deixa instalar o `.apk`.**
Permita a instalação de **fontes desconhecidas** para o app que abriu o arquivo (navegador ou gerenciador).

**A atualização não conclui no Android.**
Na primeira vez, o Android pede para **permitir que o Hubify Gaming instale atualizações**: ative e toque em **Atualizar agora** de novo. Se persistir, baixe o `.apk` pelas [Releases](https://github.com/andreygiordane/hubify-gaming-releases/releases/latest) e instale por cima (seus dados ficam na conta).

**"O arquivo baixado não confere com o SHA-256."**
O app **recusou** instalar por segurança. Tente de novo; se repetir, baixe pelas [Releases](https://github.com/andreygiordane/hubify-gaming-releases/releases/latest) e [confira o hash](INSTALACAO.md#verificar-o-arquivo-sha-256).

**O app do Windows "sumiu" ao fechar.**
O **X** só **esconde** a janela (o app fica na bandeja). Para encerrar de vez: botão direito no ícone da bandeja → **Sair**.

## Notificações

**Não recebo notificações.**
- Permita as notificações quando o app pedir (ou em **Configurações → Notificações**).
- No **iPhone/iPad**, adicione o app à **Tela de Início** primeiro (iOS 16.4 ou mais novo) e abra por lá.
- Confira se o sistema não está em modo "não perturbe" e se o site/app não está bloqueado nas permissões.

## Ainda com problema?

[Abra uma issue](https://github.com/andreygiordane/hubify-gaming-releases/issues/new/choose) contando: **plataforma e versão** (por exemplo, Windows 11, app 1.5.0), **o que você fez**, **o que esperava** e **o que aconteceu**. Se puder, anexe uma captura de tela **sem dados pessoais**.

Falha de **segurança**? Use o [relato privado](../SECURITY.md), não uma issue pública.
