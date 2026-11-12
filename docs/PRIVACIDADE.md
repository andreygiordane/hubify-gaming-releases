# Privacidade (LGPD)

[← Voltar à documentação](../README.md#documentação)

Este é um **resumo em linguagem simples**. O texto completo e vinculante está nos documentos oficiais, dentro do app (Configurações → Privacidade e termos) e na web:

- **[Política de Privacidade](https://hubify.site/site/privacidade.html)**
- **[Termos de Uso](https://hubify.site/site/termos.html)**

> O Hubify Gaming está em **beta**. As políticas podem ser atualizadas; mudanças relevantes pedem novo aceite.

## O que não fazemos

- **Não vendemos nem alugamos** seus dados.
- **Sem publicidade** e **sem rastreadores de terceiros**.
- **Não pedimos documento de identidade nem selfie.**
- **Não usamos o conteúdo** das mensagens para publicidade nem para treinar sistemas de inteligência artificial.

## O que guardamos

| Dado | Para quê |
|---|---|
| Nome de usuário, nome de exibição, **e-mail** e **senha** (só um resumo irreversível, Argon2id) | Criar e proteger a conta |
| Perfil que você preenche (foto, bio, jogos, redes, status) | Mostrar seu perfil |
| Mensagens, anexos e configurações das comunidades | Prestar o serviço |
| Jogo e música atuais (**só no app do Windows e só se você permitir**) | Mostrar no seu perfil |
| IP e tentativas de entrada | Bloquear abuso e força bruta |
| Identificação do aparelho para notificações (**se você ativar**) | Enviar avisos |
| Data e versão do aceite dos termos | Registro exigido pela LGPD |

Voz e vídeo em tempo real **não são gravados** nem guardados pelo servidor.

## Quem recebe dados (o mínimo necessário)

- **Cloudflare:** transporte e proteção do tráfego.
- **IGDB (Twitch):** enviamos **só o nome do jogo** pesquisado, nunca dados da sua conta.
- **Have I Been Pwned:** ao criar ou trocar a senha, só os **5 primeiros caracteres de um resumo** da senha (a senha nunca sai).
- **Serviços de push** dos navegadores (Google, Mozilla, Apple) e **GitHub** (consulta pública da versão do app).
- **Autoridades**, quando houver obrigação legal.

O servidor fica no **Brasil**; alguns fornecedores acima operam também fora do país (art. 33 da LGPD).

## Mensagens e criptografia

- **DMs com criptografia de ponta a ponta:** só você e a outra pessoa leem. Nem o servidor.
- **Canais de comunidades:** cifrados no armazenamento do servidor, mas a **administração tem acesso técnico**, usado só para investigar denúncias, abuso e segurança ou cumprir ordem judicial.
- **Metadados** (quem fala com quem, horários, nomes) **não** são ocultados.

Detalhes e limites: [Segurança](SEGURANCA.md#o-que-é-protegido-e-o-que-não-é).

## Por quanto tempo

Enquanto a conta existir e for necessário para o serviço. Ao pedir a exclusão da conta, removemos seus dados pessoais **em até 15 dias**, exceto o que a lei obrigar a manter. Mensagens suas em comunidades podem ser **anonimizadas** em vez de apagadas, para não quebrar conversas de outras pessoas. Registros técnicos de segurança ficam **só na memória** do servidor, por até 7 dias.

## Seus direitos

Pela LGPD (art. 18) você pode pedir:

- **confirmação** de que tratamos seus dados e **acesso** a eles;
- **correção** de dados incorretos;
- **anonimização, bloqueio ou eliminação** de dados desnecessários;
- **portabilidade** (uma **cópia dos seus dados**);
- **informação** sobre com quem compartilhamos;
- **revogação do consentimento** (por exemplo, jogo/música e notificações, que você desliga em Configurações);
- **exclusão da conta**.

Parte disso você faz sozinho em **Configurações** (editar perfil, trocar senha, desligar jogo/música e notificações, ligar 2FA). Para o restante, use o contato indicado na **Política de Privacidade** dentro do app; respondemos em até **15 dias**.

## Crianças e adolescentes

O serviço é destinado a **maiores de 14 anos**. **Menores de 18** só devem usar com o conhecimento e a autorização de um responsável legal.

## Cookies

Usamos apenas o armazenamento local do navegador/app para manter sua sessão e suas preferências (tema, atalhos, volume). **Sem cookies de publicidade ou rastreamento.**
