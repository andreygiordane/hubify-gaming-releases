# Atualizações

[← Voltar à documentação](../README.md#documentação)

Cada versão nova é publicada em **[Releases](https://github.com/andreygiordane/hubify-gaming-releases/releases)**, com o instalador, o APK e o `SHA256SUMS.txt`. Os aplicativos avisam sozinhos quando há uma versão mais nova. A **versão online** (navegador) está sempre atualizada.

## Windows

A partir da **versão 1.5.0**, a atualização é **dentro do próprio app** e **silenciosa**:

1. O app consulta a última versão em segundo plano e mostra uma faixa: *"Nova versão X disponível"*.
2. Toque em **Atualizar agora**.
3. O app **baixa**, **confere o SHA-256** contra o `SHA256SUMS.txt` da mesma versão e, só se conferir, **instala sem janelas** e **reabre sozinho** já na versão nova.
4. O **instalador baixado é apagado** (na abertura seguinte, da pasta temporária de atualização).

Segurança da atualização:

- Só aceita arquivos de **hosts oficiais do GitHub**.
- **Sem o hash publicado, recusa**; se o hash não conferir, **apaga o arquivo e não instala**.
- Nada roda sem o seu clique em **Atualizar agora**.

Quem está em uma versão **anterior à 1.5.0** vê a faixa e atualiza pelo fluxo antigo (baixa e abre o instalador); depois disso, as próximas já são silenciosas.

> Se o Windows mostrar o aviso do SmartScreen no instalador da primeira instalação, veja [Instalação](INSTALACAO.md#windows).

## Android

A partir da **versão 1.5.0**, o app também se atualiza **por dentro**:

1. Aparece o aviso *"Nova versão X disponível"* (também em **Configurações → Aplicativo e atualização**).
2. Toque em **Atualizar agora**.
3. **Na primeira vez**, o Android pede para **permitir que o Hubify Gaming instale atualizações** (uma configuração do sistema, uma única vez). Volte e toque em **Atualizar agora** de novo.
4. O app **baixa**, **confere o SHA-256**, entrega o pacote ao **instalador do Android** e **apaga o arquivo** depois.

O que o Android permite (e o que não):

- O Android **não deixa um app instalar outro sem o sistema participar**. Por isso, **na primeira atualização** o sistema pode mostrar uma **confirmação** ("Atualizar este app?").
- Em **Android 12 ou mais novo**, as atualizações seguintes costumam ocorrer **sem perguntar**, porque o próprio Hubify passa a ser o instalador de origem.
- O Android só aceita a atualização se o APK tiver a **mesma assinatura** do app instalado: um arquivo adulterado ou de outra origem é **recusado pelo sistema**.
- Ao terminar a instalação, o app é reiniciado pelo sistema. Se ele fechar, é só abrir de novo.

Quem está em versão **anterior à 1.5.0** atualiza **uma vez** baixando o `.apk` pela página de [Releases](https://github.com/andreygiordane/hubify-gaming-releases/releases/latest) (ou pelo botão do aviso); depois disso, as próximas são pelo app.

## iPhone, iPad e navegador

Não há o que instalar: a versão online **atualiza sozinha**. Se algo parecer antigo, recarregue a página (ou feche e abra o ícone da Tela de Início).

## macOS e Linux

Nestes sistemas o app **avisa** quando há versão nova e, ao tocar em **Atualizar agora**, **abre o arquivo da versão nova no navegador** para você instalar (no macOS, arrastando o novo app por cima do antigo; no Linux, trocando o AppImage ou instalando o novo `.deb`). **Não há instalação silenciosa** porque o app ainda não é assinado/notarizado pela Apple e o Linux não tem um instalador único.

## Conferindo manualmente

Prefere não atualizar pelo app? Baixe o arquivo desta página e [confira o SHA-256](INSTALACAO.md#verificar-o-arquivo-sha-256). Instalar por cima mantém seus dados: eles ficam na sua conta, no servidor.

## Notas das versões

Veja o [histórico de versões](CHANGELOG.md).
