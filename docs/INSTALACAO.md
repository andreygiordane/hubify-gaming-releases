# Instalação

[← Voltar à documentação](../README.md#documentação)

Os instaladores ficam na página de **[Releases](https://github.com/andreygiordane/hubify-gaming-releases/releases/latest)**. Todo arquivo vem com o hash SHA-256 no `SHA256SUMS.txt` da mesma versão.

| Plataforma | Arquivo | Seção |
|---|---|---|
| Windows 10/11 | `Hubify-Gaming-Setup-X.Y.Z.exe` | [Windows](#windows) |
| Android | `Hubify-Gaming-X.Y.Z.apk` | [Android](#android) |
| iPhone e iPad | sem instalador (navegador) | [iPhone e iPad](#iphone-e-ipad) |
| macOS (Apple Silicon e Intel) | `Hubify-Gaming-X.Y.Z-mac-arm64.dmg` / `-mac-x64.dmg` | [macOS](#macos) |
| Linux (x64) | `Hubify-Gaming-X.Y.Z-linux-x86_64.AppImage` ou `-linux-amd64.deb` | [Linux](#linux) |

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

## macOS

1. Baixe o arquivo certo para o seu Mac na [última versão](https://github.com/andreygiordane/hubify-gaming-releases/releases/latest):
   - **Apple Silicon** (M1, M2, M3, M4...): `Hubify-Gaming-X.Y.Z-mac-arm64.dmg`
   - **Intel**: `Hubify-Gaming-X.Y.Z-mac-x64.dmg`
   - Não sabe qual é? Menu  → **Sobre este Mac**: se aparecer *Chip Apple M…*, é Apple Silicon; se aparecer *Processador Intel*, é Intel.
   - Também há `.zip` de cada um, se preferir não usar o `.dmg`.
2. Abra o `.dmg` e **arraste o Hubify Gaming para Aplicativos**.
3. **Primeira abertura:** o app **não é notarizado pela Apple** (isso exige uma conta de desenvolvedor paga). Por isso o macOS pode dizer que não consegue verificá-lo:
   - Clique com o **botão direito** no app → **Abrir** → **Abrir**. Ou:
   - **Ajustes do Sistema → Privacidade e Segurança → Abrir mesmo assim.**
   - Se disser que o app está **"danificado"**, rode no Terminal: `xattr -dr com.apple.quarantine "/Applications/Hubify Gaming.app"`.
4. **Permissões:** o macOS pede **Microfone** (voz) e, para transmitir, **Gravação de Tela**. Para o *apertar para falar* global, ative o app em **Privacidade e Segurança → Monitoramento de Entrada** (e **Acessibilidade**, se o sistema pedir).

**Limites no macOS:** sem reconhecimento automático de jogo e música (só no Windows), sem áudio do sistema na transmissão e **sem instalação silenciosa de atualização** (o app avisa e abre o download). O app é novo e está em **beta**: se algo falhar, [abra uma issue](https://github.com/andreygiordane/hubify-gaming-releases/issues/new/choose) dizendo o modelo do Mac e a versão do macOS.

## Linux

Disponível para **x64** (a maioria dos computadores). Escolha um formato:

**AppImage** (funciona na maioria das distribuições, sem instalar):

```bash
chmod +x Hubify-Gaming-X.Y.Z-linux-x86_64.AppImage
./Hubify-Gaming-X.Y.Z-linux-x86_64.AppImage
```

Se não abrir, instale o **FUSE 2** (`libfuse2` no Ubuntu/Debian: `sudo apt install libfuse2`; no Ubuntu 24.04, `libfuse2t64`). O AppImage roda com o sandbox do Chromium desligado, por limitação do formato; o `.deb` não precisa disso.

**.deb** (Ubuntu, Debian, Mint, Pop!_OS...):

```bash
sudo apt install ./Hubify-Gaming-X.Y.Z-linux-amd64.deb
```

**Limites no Linux:**

- O *apertar para falar* global funciona em **X11**; em **Wayland** o sistema pode impedir (o atalho vale com o app em foco).
- A transmissão de tela em **Wayland** depende do portal do sistema e pode variar por distribuição.
- Sem reconhecimento automático de jogo e música, sem áudio do sistema na transmissão e sem instalação silenciosa de atualização (o app avisa e abre o download).
- Testado na compilação, mas **ainda com poucos testes em distribuições reais**: relatos ajudam muito.

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
sha256sum Hubify-Gaming-X.Y.Z-linux-x86_64.AppImage      # Linux
shasum -a 256 Hubify-Gaming-X.Y.Z-mac-arm64.dmg          # macOS
```

Se o valor for **diferente**, não instale: apague o arquivo e baixe de novo, somente desta página.

## Desinstalar

- **Windows:** Configurações → Aplicativos → *Hubify Gaming* → Desinstalar.
- **Android:** toque e segure o ícone → Desinstalar.
- **macOS:** arraste o app de Aplicativos para a Lixeira.
- **Linux:** apague o AppImage, ou `sudo apt remove hubify-gaming-desktop` se instalou o `.deb`.

Suas comunidades, mensagens e amigos ficam na sua conta (no servidor), não no aplicativo. Para apagar a conta e os dados, veja [Privacidade](PRIVACIDADE.md#seus-direitos).
