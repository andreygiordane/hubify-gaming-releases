# Mensagens e amigos

[← Voltar à documentação](../README.md#documentação)

## Mensagens diretas

Em **Mensagens** você conversa 1 para 1.

- Texto, **anexos**, **mensagens de voz** e emojis.
- **Editar** e **excluir** as suas mensagens ("Mensagem apagada" aparece para os dois lados). Só o autor edita ou apaga a própria mensagem.
- **Resposta** a uma mensagem específica e **encaminhar**.
- Indicadores de **digitando**, **enviada** e **lida**.
- **Convites em cartão**: quem convida um amigo para uma comunidade manda um cartão com botão de entrar.
- **Notificações** (opcional): o app pode avisar de novas mensagens mesmo fechado.

> Chamadas de voz e vídeo **1 para 1 estão desativadas por enquanto**. Voz e vídeo seguem funcionando nos canais das comunidades.

### Criptografia de ponta a ponta

As conversas diretas podem ter **criptografia de ponta a ponta (E2EE)**: o conteúdo é cifrado no aparelho de quem envia e só é aberto no aparelho de quem recebe. Nem o servidor nem a administração conseguem lê-lo.

- Ela é **opcional e precisa ser ativada por cada pessoa** (Configurações → Conta → Senha e segurança).
- A conversa só fica protegida quando **as duas pessoas** ativaram. Antes disso, o cadeado no topo da conversa aparece **aberto**.
- Quando as duas ativam, o cadeado fica **fechado** e o app **recusa enviar em texto aberto** (para ninguém ser rebaixado sem perceber).
- Você define uma **senha de mensagens**, diferente da senha da conta.
- Para ter certeza de que ninguém está no meio da conversa, compare o **número de segurança** (toque no cadeado) com o da outra pessoa por outro meio.

Tudo explicado, com limites, em **[Segurança](SEGURANCA.md#criptografia-de-ponta-a-ponta-nas-mensagens-diretas)**.

### Mensagens "trancadas"

Em um aparelho novo (ou depois de limpar os dados do navegador), as mensagens protegidas aparecem como **🔒 Mensagem protegida** até você digitar a **senha de mensagens**. Depois de desbloquear, o aparelho lembra e não pergunta de novo.

Se você **esquecer** a senha de mensagens, é possível **redefinir**, mas as mensagens protegidas **antigas não poderão mais ser lidas** (nem por nós). Seus contatos verão um aviso de que o seu código de segurança mudou.

## Amigos

- Cada pessoa tem um **código** (por exemplo `#0001`) em **Configurações → Conta**. Passe-o para quem quer adicionar você.
- Em **Amigos**, adicione pessoas pelo código, aceite pedidos e veja quem está online e o que está jogando.
- Do painel de **Amigos** dá para abrir uma conversa ou convidar a pessoa para uma comunidade.

## Perfil gamer

Em **Configurações → Perfil** e **Jogos e capas**:

- foto, banner, biografia e frase de status;
- **jogos favoritos**, com capa oficial, ano, gêneros e nota (dados da base **IGDB**);
- **redes** (links que você escolhe mostrar);
- seu **status** de presença (disponível, ausente...).

O jogo que você está jogando e a música que ouve (app do Windows) aparecem no perfil **somente se você permitir**.

## Privacidade das conversas

| O que | Protegido por |
|---|---|
| DMs com E2EE ativa nos dois lados | **Ponta a ponta**: só os dois leem. |
| DMs sem E2EE (a outra pessoa ainda não ativou) | HTTPS + cifra no armazenamento do servidor. |
| Canais de comunidades | HTTPS + cifra no armazenamento do servidor. |

Veja os limites em [Segurança](SEGURANCA.md#o-que-é-protegido-e-o-que-não-é).
