# Comunidades

[← Voltar à documentação](../README.md#documentação)

Uma **comunidade** é o seu servidor: um espaço com canais de texto, de voz e de palco, cargos, regras e convites.

## Criar uma comunidade

Toque no **+** ao lado de **Servidores**, escolha **Criar** e preencha:

- **Nome** e **descrição**;
- **Capa** e **ícone**;
- **Visibilidade**: **pública** (aparece no **Explorar** e qualquer pessoa pode entrar) ou **privada** (só entra quem tem convite).

Você vira o **Dono**.

## Canais

| Tipo | Para que serve |
|---|---|
| **Texto** (`#`) | Conversa escrita, com anexos, figurinhas e menções com `@`. |
| **Voz** | Sala de fala em tempo real, com **chat próprio** dentro da sala. |
| **Palco** | Poucos oradores e muitos ouvintes, com **levantar a mão** e **chamar ao palco**. |

Opções úteis de cada canal (engrenagem ao lado do nome):

- **Limite de pessoas** nas salas de voz (aparece como `00 | 21`: agora | limite). Quem gerencia canais entra mesmo com a sala cheia.
- **Sala privada**: só os cargos e as pessoas escolhidos veem e entram.
- **Sala com senha**: aparece com cadeado. Depois de 5 erros seguidos, o acesso é bloqueado por 1 minuto.
- **Modo lento**, tópico e nome.

### Categorias

Os canais ficam em **categorias**. Você pode **criar, renomear, reordenar e apagar todas**.

> **Atenção:** apagar uma categoria apaga também os **canais dentro dela** e as **mensagens** desses canais (o app avisa antes). A comunidade nunca fica sem canal: o último não pode ser apagado.

Dentro de cada categoria, os canais de texto aparecem antes dos de voz.

### Arrastar e soltar

- **Mouse:** arraste a linha do canal.
- **Celular:** use a alça `⋮⋮` ao lado do canal.

Texto só se encaixa entre textos, voz entre voz e palco entre palco. A lista rola sozinha perto das bordas.

## Cargos e permissões

| Cargo | O que pode (em resumo) |
|---|---|
| **Dono** | Tudo, inclusive configurar e apagar a comunidade. |
| **Admin** | Gerenciar canais, categorias, cargos, convites e membros. |
| **Moderador** | Moderar mensagens e membros (remover mensagens, expulsar e banir). |
| **Membro** | Conversar e participar dos canais a que tem acesso. |

Quem tem cargo mais alto gerencia quem tem cargo mais baixo, nunca o contrário.

## Convites

- **Link ou código**, **permanente** ou **temporário** (com validade e número máximo de usos).
- Para enviar a uma pessoa específica, use **Convidar amigo**: ela recebe um **cartão de convite** na conversa direta, de **uso único** e curto prazo.
- **Gerar um código novo invalida o anterior na hora.** Use isso se um link vazou.

Quem recebe o convite precisa de conta no Hubify Gaming; o cadastro também só acontece por convite ([Primeiros passos](COMECANDO.md)).

## Moderação

Clique em **qualquer membro** (no painel de membros ou na lista de uma sala de voz) para abrir o **perfil** dele. O que aparece depende do seu cargo:

| Quem você é | O que o perfil oferece |
|---|---|
| **Membro comum** | **Mensagem** e **Adicionar** (pedido de amizade). Nada de moderação. |
| **Moderador, Admin ou Dono** | Tudo acima, mais uma área **Moderação** com as ações abaixo (só para pessoas de cargo **mais baixo** que o seu). |

Ações de moderação:

- **Mover para outro canal de voz:** escolha o canal na lista (ou **arraste**, veja abaixo).
- **Expulsar:** a pessoa sai da comunidade, mas **pode voltar com um convite**.
- **Banir temporariamente:** por **1 hora, 24 horas, 7 dias ou 30 dias**. A pessoa é removida, **não consegue voltar** durante esse tempo (nem com convite) e o banimento **termina sozinho**.
- **Banir permanente:** a pessoa só volta se alguém a **desbanir**. Você pode informar um motivo (opcional).

Regras de segurança: ninguém modera quem tem cargo **igual ou mais alto** que o seu, nem a si mesmo, e **o Dono nunca pode ser banido nem expulso**. Todas as ações ficam no **registro de auditoria** da comunidade.

**Permissões por cargo:** *Expulsar e banir por tempo* e *Banir membros* e *Mover membros* são permissões separadas, que o Dono liga ou desliga em cada cargo (Configurações da comunidade → Cargos). O **Moderador padrão** de uma comunidade nova já vem com as três.

### Arrastar membros entre canais de voz

Quem tem a permissão **Mover membros** pode **arrastar** uma pessoa (do painel de membros ou da lista da sala de voz) e **soltar em outro canal de voz ou de palco**. A pessoa é movida na hora (o app dela troca de sala) e vê um aviso de que foi movida.

Limites: só dá para mover quem **já está conectado a um canal de voz**; a pessoa precisa ter acesso ao canal de destino (e a sala não pode estar cheia). Canais de texto não recebem membros. No celular, use a opção **Mover para…** no perfil (arrastar é para mouse).

Boas práticas: escreva regras em um canal `#regras`, use um canal de avisos só para a equipe e dê cargo de moderação a pessoas de confiança.

## Importar do Discord

Dá para trazer a **estrutura** de um servidor do Discord:

1. No Discord, gere um **modelo de servidor** (Configurações do servidor → Modelo de servidor).
2. No Hubify Gaming, escolha **Importar do Discord** e cole o link do modelo (`discord.new/CÓDIGO`).

Vêm: **cargos, permissões, categorias, canais, tópicos e modo lento**. **Não** vêm: mensagens, membros e imagens (o Discord não entrega isso no modelo).

## Dados e privacidade das comunidades

Mensagens de canais ficam **cifradas no armazenamento do servidor**, mas **não** têm criptografia de ponta a ponta: veja [o que é protegido e o que não é](SEGURANCA.md#o-que-é-protegido-e-o-que-não-é).
