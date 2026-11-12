# Segurança

[← Voltar à documentação](../README.md#documentação)

Esta página explica **como o Hubify Gaming protege você**, o que cada proteção cobre e, com a mesma clareza, **o que ela não cobre**. Para relatar uma falha, veja a [política de segurança](../SECURITY.md).

> Esta página também está no site, com um diagrama: **[hubify.site/site/documentacao.html#seguranca](https://hubify.site/site/documentacao.html#seguranca)**.

> O Hubify Gaming está em **beta**. Levamos segurança a sério, mas nenhum sistema é 100% imune. Se algo parecer estranho, avise.

## Índice

1. [Visão geral](#visão-geral)
2. [Conta e login](#conta-e-login)
3. [Verificação em duas etapas (2FA)](#verificação-em-duas-etapas-2fa)
4. [Criptografia de ponta a ponta nas mensagens diretas](#criptografia-de-ponta-a-ponta-nas-mensagens-diretas)
5. [O que é protegido e o que não é](#o-que-é-protegido-e-o-que-não-é)
6. [Proteção do servidor](#proteção-do-servidor)
7. [Proteção dos aplicativos](#proteção-dos-aplicativos)
8. [O que você pode fazer](#o-que-você-pode-fazer)

## Visão geral

| Camada | Proteção |
|---|---|
| **Entrada** | Cadastro só por convite + código de 6 dígitos por e-mail. |
| **Login** | Senhas com Argon2id, bloqueio de senhas comuns/vazadas, limite de tentativas, **2FA opcional**. |
| **Mensagens diretas** | **Criptografia de ponta a ponta** (opcional por pessoa), número de segurança e aviso de troca de chave. |
| **Tudo que trafega** | HTTPS (TLS) entre você e o servidor. |
| **Dados no servidor** | Conteúdo cifrado em repouso (AES-256-GCM) e segredos fora do código. |
| **Aplicativos** | Atualizações conferidas por SHA-256; instalação de atualização só de fontes oficiais. |

## Conta e login

- **Convite obrigatório** e **verificação do e-mail** com código de 6 dígitos (vale 10 minutos, uso único; só guardamos um resumo irreversível dele).
- **Senhas** guardadas com **Argon2id** (nunca em texto). O tamanho é o que mais importa: mínimo de 8 caracteres, e uma **frase longa** é mais forte. Senhas comuns e as que já apareceram em **vazamentos** são recusadas (a checagem usa *k-anonymity*: só os 5 primeiros caracteres de um resumo saem do servidor, a senha nunca).
- **Limite de tentativas:** erros seguidos bloqueiam o acesso por um tempo, por usuário e por origem.
- **Sessões** usam tokens assinados e **deixam de valer** quando você troca a senha. Trocar a senha exige a senha atual.
- Contas e dados de outras pessoas **não** ficam acessíveis pela API: cada pessoa só enxerga o que lhe pertence.

## Verificação em duas etapas (2FA)

A 2FA **é opcional**: com ela, entrar exige a senha **e** um código de 6 dígitos de um **aplicativo autenticador** (Google Authenticator, Microsoft Authenticator, Authy, 1Password, Bitwarden...).

### Ativar

1. **Configurações → Conta → Senha e segurança → Verificação em duas etapas → Ativar.**
2. Escaneie o **QR code** com o autenticador (ou digite a chave manual).
3. Digite o código de 6 dígitos mostrado pelo app.
4. **Guarde os 8 códigos de recuperação** (copie ou baixe). Eles aparecem **uma única vez**.

### Como funciona

- Depois da senha certa, o servidor pede o código. **Senha certa sozinha não entra.**
- O **mesmo código não pode ser usado duas vezes** (proteção contra reaproveitamento).
- **5 códigos errados** bloqueiam as tentativas por 15 minutos.
- O segredo do autenticador é guardado **cifrado** no servidor; os códigos de recuperação, só como **resumo irreversível**.
- **Perdeu o celular?** Use um **código de recuperação** no lugar do código do app (cada um vale uma vez).
- **Desligar** a 2FA exige a **senha** e um **código atual**.

> Sem o app autenticador **e** sem os códigos de recuperação, não há como entrar na conta. Guarde os códigos em um lugar seguro (por exemplo, um gerenciador de senhas).

## Criptografia de ponta a ponta nas mensagens diretas

### O que é

Em uma conversa com criptografia de ponta a ponta (E2EE), o conteúdo (texto, anexos e figurinhas) é **cifrado no seu aparelho** antes de sair e só é **decifrado no aparelho da outra pessoa**. O servidor só guarda e repassa um envelope ilegível. **Nem o servidor, nem a administração, nem quem invadir o banco de dados consegue ler as mensagens.**

### Como ativar

**Configurações → Conta → Senha e segurança → Criptografia de ponta a ponta → Ativar.** Você cria uma **senha de mensagens** (use 10 caracteres ou mais; uma frase serve) e confirma que entende que, se a esquecer, as mensagens protegidas antigas não podem ser recuperadas.

A conversa só fica protegida quando **as duas pessoas** ativam. O **cadeado** no topo da conversa mostra o estado:

| Cadeado | Significa |
|---|---|
| 🔒 verde, fechado | Protegida de ponta a ponta. |
| 🔓 cinza, aberto | A outra pessoa ainda não ativou (ou você não). |
| 🔒 amarelo | O **código de segurança mudou**: confira com a pessoa. |

### Como funciona (por dentro)

Para quem gosta de detalhes:

- Cada pessoa tem um **par de chaves ECDH P-256**. A **chave pública** fica no servidor; a **privada** nunca sai do aparelho em texto aberto. Para estar disponível em outros aparelhos, ela é guardada no servidor **já cifrada** (AES-256-GCM) com uma chave derivada da **senha de mensagens** por **PBKDF2-SHA-256 com 600 mil voltas**. O servidor **não conhece** essa senha.
- Cada mensagem usa uma **chave AES-256-GCM própria**. Essa chave é "embrulhada" para cada participante (inclusive você, para reler em outro aparelho) usando **HKDF sobre dois segredos ECDH**: um efêmero (muda a cada mensagem) e um entre a chave de quem envia e a de quem recebe. O segundo **autentica o remetente**: ninguém, nem o servidor, consegue forjar uma mensagem em nome de outra pessoa.
- O **id, a sala e o remetente** entram como dados autenticados: o servidor não consegue **mover** uma mensagem cifrada para outra conversa.
- Tudo usa a API criptográfica nativa do navegador/sistema (**WebCrypto**), sem bibliotecas externas.
- **Sem rebaixamento:** quando os dois lados têm chaves, **o servidor recusa texto aberto** e o app também não envia.

### Número de segurança

Toque no cadeado para ver um **número de segurança** (12 grupos de 5 dígitos). Ele deve ser **idêntico** nos dois aparelhos. Compare **por outro meio** (pessoalmente ou por ligação): se for igual, ninguém está no meio da conversa.

Se o número **mudar**, o app avisa. Isso acontece quando a pessoa **redefine** a criptografia, troca de conta ou, em tese, quando alguém tenta interceptar. Confira antes de continuar falando de assuntos delicados.

### Aparelho novo, senha esquecida

- **Aparelho novo:** entre na conta e digite a **senha de mensagens**. O aparelho então lembra (a chave fica guardada nele, sem poder ser exportada) e não pergunta de novo, até você **sair da conta** (aí a chave local é apagada).
- **Esqueci a senha de mensagens:** dá para **redefinir** (exige a senha da conta). Isso cria chaves novas e **as mensagens protegidas antigas deixam de poder ser lidas**, por todos, inclusive por nós. É o preço de ninguém, além de você, conseguir abri-las.

## O que é protegido e o que não é

Dizemos isto com franqueza para você decidir o que conversar onde:

| | E2EE nas DMs | Canais de comunidades | Metadados |
|---|---|---|---|
| **Conteúdo** (texto, anexos) | ✅ só os dois leem | ⚠️ cifrado no servidor, mas **a administração tem acesso técnico** | — |
| **Quem fala com quem, quando, tamanho** | ❌ visível ao servidor | ❌ visível ao servidor | ❌ |
| **Nomes, perfis, convites, amizades** | — | — | ❌ visíveis ao servidor |

Limites que você precisa conhecer:

- **Canais de comunidades não têm E2EE.** Servem a conversas de grupo com moderação (remover mensagens, banir), que exigem que o servidor entenda o conteúdo. O conteúdo é **cifrado no armazenamento** e o acesso da administração só é usado para investigar denúncias, abuso e segurança, ou cumprir ordem judicial.
- **Metadados** (quem conversa com quem, horários, tamanhos, nomes) **não** são ocultados.
- A E2EE **não protege um aparelho comprometido**: se alguém controla seu celular ou computador (vírus, acesso físico), enxerga o que você enxerga.
- **Capturas de tela e cópias** feitas pela outra pessoa estão fora do alcance de qualquer criptografia.
- **Voz e vídeo** usam a criptografia padrão do WebRTC **entre os aparelhos**, mas isso **não** é o mesmo que a E2EE das mensagens.
- **Notificações push** (com o app fechado) de mensagens com E2EE **não mostram o texto** (aparece "Nova mensagem"), porque o servidor não consegue lê-lo. Com o app aberto, o próprio aparelho decifra e pode avisar com o texto.
- Antes de a outra pessoa ativar, a conversa **não é** de ponta a ponta.

## Proteção do servidor

- **Dados em repouso cifrados** (AES-256-GCM) e **segredos em cofre**, fora do código e do banco.
- **Tráfego protegido** por HTTPS; o acesso público passa por um túnel da Cloudflare, e o servidor **não expõe portas web** para a internet.
- **Cabeçalhos de segurança** (CSP restritiva, X-Frame-Options, HSTS, Permissions-Policy, entre outros) e **limites de requisição** por origem.
- **Autorização em cada chamada:** cada pessoa só lê e altera o que é dela. As mensagens só podem ser **editadas ou apagadas pelo autor**.
- **Painel de monitoramento** para a administração: tentativas de invasão, varredura de endereços e bloqueios aparecem em tempo real.
- **Backups cifrados** com chave que o servidor não possui (só quem administra consegue restaurar).
- Sistema operacional com **atualizações automáticas de segurança**, firewall e bloqueio de tentativas de acesso por força bruta.

## Proteção dos aplicativos

- **Windows:** atualização só de **fontes oficiais** do GitHub e **somente se o SHA-256 do instalador conferir** com o publicado.
- **Android:** o app só aceita baixar atualizações de **hosts oficiais** do GitHub, confere o **SHA-256** e o **próprio Android recusa** instalar um APK que não tenha a **mesma assinatura** do app já instalado.
- **Instalador do Windows ainda sem assinatura digital paga** (o SmartScreen pode avisar). Confira o [SHA-256](INSTALACAO.md#verificar-o-arquivo-sha-256) do arquivo antes de instalar.

## O que você pode fazer

1. **Ative a 2FA** e **a criptografia de ponta a ponta** (Configurações → Conta → Senha e segurança).
2. Use **senhas longas e únicas** (um gerenciador de senhas ajuda) e uma **senha de mensagens diferente da senha da conta**.
3. **Confira o número de segurança** com as pessoas com quem você conversa assuntos sensíveis.
4. **Baixe os apps só desta página** e confira o SHA-256.
5. **Não compartilhe** links de convite em lugares públicos (se vazar, gere um novo: o antigo deixa de valer na hora).
6. Desconfie de mensagens que peçam códigos, senhas ou "verificação" fora do app.
7. Mantenha o aparelho **atualizado** e com bloqueio de tela.

Para saber como tratamos seus dados pessoais, veja [Privacidade](PRIVACIDADE.md).
