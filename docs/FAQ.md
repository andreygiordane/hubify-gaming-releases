# Perguntas frequentes

[← Voltar à documentação](../README.md#documentação)

## Geral

**O Hubify Gaming é gratuito?**
Hoje o acesso é por convite e não há cobrança.

**Está pronto?**
Está em **beta**: já dá para usar no dia a dia, mas ainda estamos trabalhando em melhorias e novidades. Podem aparecer falhas e mudanças pelo caminho. Relatar problemas ajuda a corrigir mais rápido ([abra uma issue](https://github.com/andreygiordane/hubify-gaming-releases/issues/new/choose)).

**Em quais plataformas funciona?**
Windows (app), Android (app) e **qualquer navegador moderno** (inclusive iPhone, iPad, macOS e Linux). Clientes para macOS e Linux estão em preparação.

**Tem app na App Store ou na Google Play?**
Ainda não. No Android, o `.apk` é baixado desta página; no iPhone e iPad, use a versão online no Safari ([guia](INSTALACAO.md#iphone-e-ipad)).

**Por que só por convite?**
Para manter as comunidades seguras e evitar contas em massa. Quem já está na plataforma gera um link de convite.

## Conta

**Como crio uma conta?**
Abra um link de convite (`hubify.site/?convite=CÓDIGO`), informe seus dados, confirme o e-mail com o código de 6 dígitos e aceite os termos. Passo a passo em [Primeiros passos](COMECANDO.md).

**O código de e-mail não chega.**
Confira o spam e o endereço digitado, espere alguns instantes e use **Reenviar código** (há um intervalo entre os envios). O código vale 10 minutos.

**Esqueci minha senha.**
Peça ajuda a quem administra a plataforma (a recuperação automática por e-mail ainda não existe). Se você usa **2FA**, tenha à mão os códigos de recuperação.

**Posso mudar o e-mail ou o nome de usuário?**
O nome de exibição e o perfil você edita em **Configurações → Conta** e **Perfil**. Para mudar usuário ou e-mail, veja as opções em Configurações → Conta; se a mudança não estiver disponível lá, fale com a administração.

**Como apago minha conta e meus dados?**
Peça pelo contato da [Política de Privacidade](PRIVACIDADE.md#seus-direitos). Removemos seus dados pessoais em até 15 dias.

## Segurança

**O que é a 2FA e preciso dela?**
É um segundo passo no login (código do app autenticador). **É opcional**, mas recomendada. [Como ativar](SEGURANCA.md#verificação-em-duas-etapas-2fa).

**Perdi o celular do autenticador.**
Entre com um **código de recuperação** (os 8 que você guardou ao ativar). Cada um vale uma vez. Sem eles e sem o app, não há como entrar.

**O que é a criptografia de ponta a ponta? Todas as conversas têm?**
Só as **mensagens diretas 1 para 1**, e só quando **as duas pessoas ativaram**. Canais de comunidades **não** têm. [Entenda os limites](SEGURANCA.md#o-que-é-protegido-e-o-que-não-é).

**Esqueci a senha de mensagens. E agora?**
Dá para **redefinir**, mas as mensagens protegidas antigas **não poderão mais ser lidas** (nem por nós). É assim por projeto: se nós conseguíssemos recuperar, o servidor também poderia ler.

**O administrador pode ler minhas mensagens?**
- **DMs com E2EE:** não.
- **Canais de comunidades e DMs sem E2EE:** tecnicamente, sim (estão cifradas no armazenamento, mas o servidor consegue abri-las). O acesso só é usado para investigar denúncias, abuso e segurança, ou por ordem judicial.

**Por que o Windows avisa sobre o instalador?**
O instalador ainda não tem assinatura digital paga, então o SmartScreen mostra um aviso para programas novos. Confira o [SHA-256](INSTALACAO.md#verificar-o-arquivo-sha-256) e use **Mais informações → Executar assim mesmo**.

**O app lê o que eu faço no computador?**
Não. O **status automático** (opcional) lê **só** o nome do programa em execução e o título/artista que o Windows já exibe no controle de mídia. Nada é lido de dentro dos jogos, e o app **não injeta código** neles.

**Isso pode dar problema com anti-cheat?**
O app não lê a memória nem injeta código em jogos, e só observa janelas e processos como qualquer programa comum. Ainda assim, cada anti-cheat tem as próprias regras: se tiver dúvida sobre um jogo específico, desative o status automático.

## Uso

**Como transmito meu jogo?**
Entre em um canal de voz e use **Transmitir** (app do Windows e navegador). No Android não é possível transmitir. [Detalhes](VOZ-E-TRANSMISSAO.md#transmitir-o-jogo).

**Posso ligar para um amigo (chamada 1 para 1)?**
Ainda não: as chamadas diretas estão **desativadas por enquanto**. Use um canal de voz da comunidade.

**Dá para trazer meu servidor do Discord?**
Dá para importar a **estrutura** (cargos, categorias, canais, tópicos e modo lento) por modelo. Mensagens, membros e imagens **não** vêm. [Como](COMUNIDADES.md#importar-do-discord).

**Como convido alguém?**
Gere um link ou código de convite na sua comunidade, ou use **Convidar amigo** para mandar um cartão de convite. [Convites](COMUNIDADES.md#convites).

**Posso usar em mais de um aparelho?**
Sim. A mesma conta funciona no computador, no celular e no navegador. Para as DMs com E2EE, digite a **senha de mensagens** em cada aparelho novo.

## Atualizações

**Como atualizo?**
O app avisa e atualiza por dentro (Windows e Android, a partir da 1.5.0). [Veja como](ATUALIZACOES.md).

**Atualizar apaga meus dados?**
Não. Seus dados ficam na conta, no servidor.

---

Não achou a resposta? Veja [Solução de problemas](SOLUCAO-DE-PROBLEMAS.md) ou [abra uma issue](https://github.com/andreygiordane/hubify-gaming-releases/issues/new/choose).
