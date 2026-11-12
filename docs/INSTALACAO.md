# Instalação

[← Voltar à documentação](../README.md#documentação)

Os instaladores ficam na página de **[Releases](https://github.com/andreygiordane/hubify-gaming-releases/releases/latest)**. Todo arquivo vem com o hash SHA-256 no `SHA256SUMS.txt` da mesma versão.

| Plataforma | Arquivo | Seção |
|---|---|---|
| Windows 10/11 | `Hubify-Gaming-Setup-X.Y.Z.exe` | [Windows](#windows) |
| Android | `Hubify-Gaming-X.Y.Z.apk` | [Android](#android) |
| iPhone e iPad | sem instalador (navegador) | [iPhone e iPad](#iphone-e-ipad) |
| macOS e Linux | em preparação | [macOS e Linux](#macos-e-linux) |

## Windows

1. Baixe o `Hubify-Gaming-Setup-X.Y.Z.exe` da [última versão](https://github.com/andreygiordane/hubify-gaming-releases/releases/latest).
2. Execute o arquivo. O instalador é **por usuário**: não pede senha de administrador.
3. Se aparecer o aviso azul do **SmartScreen** ("O Windows protegeu o computador"), clique em **Mais informações → Executar assim mesmo**.

**Por que o aviso aparece?** O instalador ainda **não tem assinatura digital paga**, e o SmartScreen desconfia de programas novos e sem assinatura. Isso não significa que o arquivo esteja adulterado: confira a integridade abaixo.

O que o app do Windows traz a mais que o navegador:

- janela com barra própria e **bandeja do sistema** (o **X** só esconde a janela; para encerrar de vez, botão direito no ícone → **Sair**);
- **apertar para falar global**, em qualquer janela (só a tecla que você escolher é monitorada);
- **status automático** do jogo e da música, **opcional** e com permissão;
- **atualização automática** (veja [Atualizações](ATUALIZACOES.md)).

## Android

1. No celular, baixe o `Hubify-Gaming-X.Y.Z.apk` da [última versão](https://github.com/andreygiordane/hubify-gaming-releases/releases/latest).
2. Abra o arquivo. O Android vai pedir para **permitir a instalação de fontes desconhecidas** para o navegador (ou gerenciador de arquivos) que você usou: permita e volte.
3. Toque em **Instalar**.

Observações:

- O app tem ícone próprio, usa o microfone nos canais de voz e envia notificações.
- **Compartilhar tela não está disponível no Android** (limitação do sistema).
- Para atualizar, veja [Atualizações](ATUALIZACOES.md#android).

## iPhone e iPad

Ainda **não existe app na App Store**. Por enquanto, use a versão online, que se comporta como um aplicativo:

1. Abra **[hubify.site/entrar](https://hubify.site/entrar)** no **Safari** e entre com sua conta.
2. Para abrir em tela cheia, com ícone próprio: toque em **Compartilhar → Adicionar à Tela de Início** e confirme.
3. Abra o Hubify Gaming pelo novo ícone.

Notificações no iPhone exigem **iOS 16.4 ou mais novo** e o app adicionado à Tela de Início. Em outros navegadores do iPhone, use o Safari para instalar.

## macOS e Linux

Estamos preparando clientes para **macOS** e **Linux**. Enquanto isso, o Hubify Gaming funciona **normalmente no navegador** nesses sistemas: [hubify.site/entrar](https://hubify.site/entrar).

Diferenças esperadas quando os apps chegarem (por limites dos sistemas): sem *apertar para falar global* e sem reconhecimento automático de jogo e música, que hoje existem só no Windows.

## Verificar o arquivo (SHA-256)

Recomendado para quem baixa instaladores de qualquer lugar. Compare o hash do arquivo que você baixou com o que está no `SHA256SUMS.txt` da mesma versão.

**Windows (PowerShell):**

```powershell
Get-FileHash .\Hubify-Gaming-Setup-X.Y.Z.exe -Algorithm SHA256
# ou
certutil -hashfile Hubify-Gaming-Setup-X.Y.Z.exe SHA256
```

**Linux / macOS:**

```bash
sha256sum Hubify-Gaming-X.Y.Z.apk      # Linux
shasum -a 256 Hubify-Gaming-X.Y.Z.apk  # macOS
```

Se o valor for **diferente**, não instale: apague o arquivo e baixe de novo, somente desta página.

## Desinstalar

- **Windows:** Configurações → Aplicativos → *Hubify Gaming* → Desinstalar.
- **Android:** toque e segure o ícone → Desinstalar.

Suas comunidades, mensagens e amigos ficam na sua conta (no servidor), não no aplicativo. Para apagar a conta e os dados, veja [Privacidade](PRIVACIDADE.md#seus-direitos).
