# Histórico de versões

[← Voltar à documentação](../README.md#documentação)

Os arquivos de cada versão estão em [Releases](https://github.com/andreygiordane/hubify-gaming-releases/releases). Todas trazem `SHA256SUMS.txt`.

## 1.5.0 · Segurança em dobro e atualização por dentro

**Segurança**
- **Verificação em duas etapas (2FA) opcional**, com app autenticador (QR code), **8 códigos de recuperação**, proteção contra reaproveitamento de código e bloqueio após erros.
- **Criptografia de ponta a ponta nas mensagens diretas** (opcional por pessoa), com **senha de mensagens**, **número de segurança** para conferência, aviso quando o código de segurança de um contato muda e **recusa de envio em texto aberto** quando os dois lados têm chaves.
- **Correções no servidor:** cada pessoa só lê as **próprias** mensagens diretas pela API; mensagens só podem ser **editadas ou apagadas pelo autor**, na conversa a que pertencem; uma mensagem existente não pode ser sobrescrita reaproveitando o id.
- Limite de mensagens por aparelho (anti-spam) e remoção de pontos de acesso desnecessários na API.
- Backups diários **cifrados** do servidor.

**Atualização dentro do app**
- **Windows:** **Atualizar agora** baixa, confere o SHA-256, **instala em silêncio**, **reabre o app** e **apaga o instalador**.
- **Android:** o app baixa, confere o SHA-256, entrega ao instalador do sistema e **apaga o APK**. A primeira vez pede uma permissão do Android; em Android 12+ as seguintes costumam passar sem perguntar.

**macOS e Linux**
- **Novos apps:** macOS (`.dmg` para Apple Silicon e Intel, e `.zip`) e Linux (`.AppImage` e `.deb`). Beta: ainda com poucos testes em computadores reais. Veja [Instalação](INSTALACAO.md#macos).

**Comunidades**
- **Clique no membro** para abrir o perfil: todos veem *Mensagem* e *Adicionar*; **Moderador, Admin e Dono** também veem **Mover, Expulsar, Banir temporariamente (1 hora a 30 dias) e Banir permanente**.
- **Arrastar e soltar membros** entre canais de voz e de palco (nova permissão **Mover membros**).
- Banimento temporário expira sozinho; o Moderador padrão agora também pode banir.

**Convites**
- **Cada link de convite vale de 5 a 10 entradas** e depois expira (não existe mais link ilimitado). O uso é contado no cadastro.
- **Saldo de convites por pessoa** (3 para contas novas): criar link, gerar link novo ou criar comunidade gasta 1. Quando acabam, é preciso aguardar novos convites serem lançados.
- A administração (Master) pode **lançar novos convites** para todas as contas.

**Voz**
- A dica do ping separa **"até o servidor"** de **"entre jogadores"** e mostra se a conexão é **direta** ou **por retransmissão**.

**Interface**
- **Apertar para falar nas configurações de voz** (Configurações → Voz e vídeo): ligar, **gravar o atalho** e ajustar o **atraso após soltar**.
- **Telas de entrada e de criar conta redesenhadas**, com painel de marca em telas largas, convite em destaque e passo do código da 2FA.
- Aviso de **beta** no app e no site.
- Nova **página inicial** em [hubify.site](https://hubify.site) e uma página de **[Documentação](https://hubify.site/site/documentacao.html)** com a segurança explicada em detalhes (a documentação completa também está neste repositório).

**Políticas:** Termos e Política de Privacidade atualizados (versão 1.4) para refletir a criptografia de ponta a ponta, a 2FA e o estado beta.

## 1.4.1
- **Senha com no mínimo 8 caracteres** no cadastro e na troca de senha (antes eram 12). Senhas comuns ou vazadas continuam recusadas.
- Mensagens e indicadores de força da senha atualizados.

## 1.4.0
- **Cadastro por convite com e-mail verificado** funcionando de ponta a ponta: o código de 6 dígitos é enviado de verdade.
- **E-mail novo e organizado**: banner, código em destaque, passo a passo e aviso de segurança, em qualquer cliente de e-mail.
- Aviso de atualização no Android e tela **Aplicativo e atualização**.

## 1.3.0
- Envio do **código de verificação por e-mail** mais simples e confiável.
- **Android:** tela de atualização em Configurações → Aplicativo e atualização, e aviso no topo.

## 1.2.0
- **Cadastro mais seguro:** além do convite, confirmação do e-mail com **código de 6 dígitos**.
- **Painel de monitoramento** (conta Master): fluxo em tempo real e alertas de ataque.
- **Categorias de verdade** e **arrastar e soltar** canais (mouse e toque).
- Aceite dos **Termos e da Política de Privacidade** (LGPD) no cadastro.
- Aviso de atualização no app Android.

## 1.1.0
- **Windows:** barra de título própria, **bandeja do sistema**, **atualização automática** com conferência de SHA-256, reconhecimento de jogo e música (opcional) e **apertar para falar global**.
- **Android:** primeiro app assinado, com ícone próprio, microfone e notificações.
- Cadastro só por convite, com aceite dos Termos; dados cifrados no servidor e senhas com Argon2id.
