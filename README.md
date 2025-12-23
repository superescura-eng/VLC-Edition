# Documentação do VLC Media Player

## 1. Visão Geral
O **VLC** é um reprodutor de mídia e motor multimídia livre e de código aberto, focado em reproduzir tudo e executar em qualquer lugar.
- **Capacidades**: Reproduz a maioria dos arquivos multimídia, discos, streams e dispositivos. Também converte, codifica e manipula streams.
- **Missão**: O VideoLAN é uma organização sem fins lucrativos. O VLC é gratuito, sem spyware, sem anúncios e sem rastreamento de usuário.
- **libVLC**: O motor do VLC pode ser incorporado em aplicações de terceiros (chamado libVLC).
- **Projeto**: Parte do projeto VideoLAN, desenvolvido por uma comunidade de voluntários.

## 2. Outros Projetos VideoLAN
Além do VLC, o projeto VideoLAN mantém diversas outras ferramentas e bibliotecas importantes para o ecossistema multimídia:
- **VLMC**: *VideoLAN Movie Creator*, software de edição de vídeo não-linear.
- **dav1d**: Decodificador AV1 rápido e eficiente.
- **DVBlast**: Aplicação de demux e streaming MPEG-2/TS.
- **x264** / **x265**: Bibliotecas para codificação H.264/AVC e H.265/HEVC.
- **multicat**: Manipulação de streams multicast e TS.
- **Bibliotecas Principais**: libdvdcss, libdvdnav, libbluray, libdvbpsi, libaacs, biTStream.

## 3. Licença
- **VLC**: GPLv2 (ou posterior). Em algumas plataformas, é *de facto* GPLv3 devido a dependências.
- **libVLC**: LGPLv2 (ou posterior), permitindo incorporação em aplicações de terceiros com outras licenças.

## 4. Plataformas Suportadas
O VLC está disponível para uma ampla gama de plataformas:
- **Windows**: Windows 7 e posteriores (incluindo UWP, Windows 10 e versões ARM 64).
- **macOS**: 10.10 e posteriores (incluindo suporte a Apple Silicon).
- **GNU/Linux**: Diversas distribuições (Debian, Ubuntu, Fedora, etc.).
- **Android**: 4.2 e posteriores (incluindo Android TV e Auto).
- **iOS**: 9 e posteriores (incluindo AppleTV e iPadOS).
- **Outros**: BSD, Haiku, OS/2.

> **Nota**: Os aplicativos para Android e iOS possuem repositórios próprios, separados do repositório principal.

## 5. Contribuição e Comunidade
O VLC é mantido por uma comunidade de voluntários; o projeto VideoLAN não paga ninguém.
- **Linguagens**: O desenvolvimento principal é em **C**, mas o repositório também contém C++, Obj-C, Assembly e Rust.
- **Onde Contribuir**: As contribuições são feitas via *Merge Requests* no [GitLab do VideoLAN](https://code.videolan.org/videolan/vlc/). Pull Requests no GitHub são ignorados.
- **Áreas para ajuda**:
    - Codificação (Coding)
    - Empacotamento (Packaging) para Windows, macOS e Linux
    - Documentação técnica
    - Design
    - Suporte e gestão de comunidade

## 6. Documentação do Usuário
O VLC possui um guia oficial de usuário detalhado, cobrindo diversos tópicos e plataformas.
- **Guia do Usuário**: [Acesse aqui](https://docs.videolan.me/vlc-user/en/index.html)
- **Seções Principais**:
    - [Desktop (Windows, macOS, Linux)](https://docs.videolan.me/vlc-user/desktop/index.html)
    - [Android](https://docs.videolan.me/vlc-user/android/index.html)
    - [iOS](https://docs.videolan.me/vlc-user/ios/index.html)
    - [FAQ & Suporte](https://docs.videolan.me/vlc-user/en/support/index.html)
    - [Glossário](https://docs.videolan.me/vlc-user/en/glossary/index.html)

## 7. Documentação para Desenvolvedores
Se você deseja contribuir com código, design ou documentação, o VLC possui um portal dedicado e um wiki extenso.
- **Portal do Desenvolvedor**: [epirat.videolan.me/devdocs](https://epirat.videolan.me/devdocs/)
- **Wiki dos Desenvolvedores**: [Developer's Corner](https://wiki.videolan.org/Developers_Corner)
- **Nightly Builds**: [Baixar Versões de Teste](https://nightlies.videolan.org/)
- **Áreas de Contribuição**:
    - **Scripting Lua**: Extensões, descoberta de serviços, playlists e metadados.
    - **Módulos C/C++**: Núcleo do VLC e maioria dos módulos.
    - **Design/Escrita**: Design de interface e melhorias na documentação.
    - **Portes do VLC**: Android, iOS e WinRT.
    - **Web Developers**: Interface Web do VLC e site do VideoLAN.
- **Começando**: [Guia de Introdução e Git](https://epirat.videolan.me/devdocs/docs/intro/git)
- **Reportar Bugs**: [Diretrizes para reportar bugs](https://epirat.videolan.me/devdocs/docs/intro/bugreports)

## 8. Recursos Adicionais
- **Site Oficial**: [videolan.org](https://videolan.org)
- **Wiki Oficial**: [wiki.videolan.org](https://wiki.videolan.org/)
- **IRC**: Canal `#videolan` no [Libera.chat](https://libera.chat)
- **Listas de Email**: [Mailing Lists](https://www.videolan.org/developers/lists.html)
