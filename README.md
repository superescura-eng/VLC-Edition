# 📺 Documentação Completa do VLC Media Player e Projetos VideoLAN

> **Última atualização:** 23 de Dezembro de 2024  
> **Licença da Documentação:** CC-BY-SA 4.0

---

## 📋 Índice

1. [Introdução ao VideoLAN](#introdução-ao-videolan)
2. [VLC Media Player](#vlc-media-player)
3. [libVLC - Engine de Multimídia](#libvlc---engine-de-multimídia)
4. [VLC for Unity](#vlc-for-unity)
5. [Bibliotecas de Decodificação](#bibliotecas-de-decodificação)
   - [libdvdcss](#libdvdcss)
   - [libdvdnav & libdvdread](#libdvdnav--libdvdread)
   - [libbluray](#libbluray)
   - [libdca](#libdca)
6. [Bibliotecas de Streaming](#bibliotecas-de-streaming)
   - [libdvbpsi](#libdvbpsi)
   - [biTStream](#bitstream)
7. [Ferramentas de Streaming](#ferramentas-de-streaming)
   - [DVBlast](#dvblast)
   - [Multicat](#multicat)
8. [Codificador de Vídeo](#codificador-de-vídeo)
   - [x264](#x264)
9. [Documentação para Desenvolvedores](#documentação-para-desenvolvedores)
10. [Links e Recursos](#links-e-recursos)

---

## Introdução ao VideoLAN

O **VideoLAN** é um projeto de software livre e código aberto que desenvolve software e bibliotecas para multimídia. O projeto foi iniciado na universidade **École Centrale Paris** (atualmente CentraleSupélec) e relicenciou o VLC sob a licença GPLv2 em fevereiro de 2001.

### 🎯 Missão do Projeto

- Desenvolver software multimídia gratuito e de código aberto
- Fornecer soluções multiplataforma para reprodução e streaming
- Criar bibliotecas reutilizáveis para desenvolvedores
- Manter uma comunidade ativa de colaboradores

### 🌐 Organização

A **VideoLAN é uma organização sem fins lucrativos**. Todos os custos são cobertos por doações dos usuários, e nenhum desenvolvedor é remunerado diretamente pela organização.

**Canais de Comunicação:**
- IRC: `#videolan` no [Libera.chat](https://libera.chat)
- Twitter: [@videolan](https://twitter.com/videolan)
- Facebook: [vlc.media.player](https://facebook.com/vlc.media.player)
- Mastodon: [@videolan@floss.social](https://floss.social/@videolan)

---

## VLC Media Player

### 📖 Visão Geral

O **VLC** é um reprodutor de mídia livre e de código aberto, focado em **reproduzir tudo** e **rodar em qualquer lugar**.

> "VLC is a libre and open source media player and multimedia engine, focused on playing everything, and running everywhere."

### ✨ Características Principais

| Recurso | Descrição |
|---------|-----------|
| **Formatos** | Reproduz a maioria dos arquivos multimídia, discos, streams e dispositivos |
| **Conversão** | Converte, codifica, transmite e manipula streams em diversos formatos |
| **Portabilidade** | Disponível para desktop, mobile e TVs |
| **Código Aberto** | Desenvolvido e mantido por uma comunidade de voluntários |

### 💻 Plataformas Suportadas

#### Desktop
| Sistema | Versão Mínima |
|---------|---------------|
| Windows | 7 ou posterior (incluindo UWP e Windows 10) |
| macOS | 10.10 (Yosemite) ou posterior |
| GNU/Linux | Diversas distribuições |
| BSD | FreeBSD e variantes |
| Haiku, OS/2 | Versões específicas |

#### Mobile
| Sistema | Versão Mínima |
|---------|---------------|
| Android | 4.2 ou posterior (inclui Android TV e Auto) |
| iOS | 9 ou posterior (inclui Apple TV e iPadOS) |

### 📥 Downloads

**Versão Atual: 3.0.21**

| Plataforma | Link de Download |
|------------|------------------|
| Windows 32-bit | [vlc-3.0.21-win32.exe](https://get.videolan.org/vlc/3.0.21/win32/vlc-3.0.21-win32.exe) |
| Windows 64-bit | [vlc-3.0.21-win64.exe](https://get.videolan.org/vlc/3.0.21/win64/vlc-3.0.21-win64.exe) |
| Windows ARM64 | [Nightly builds](https://artifacts.videolan.org/vlc/nightly-win64-arm-llvm/) |
| macOS Intel | [vlc-3.0.21-intel64.dmg](https://get.videolan.org/vlc/3.0.21/macosx/vlc-3.0.21-intel64.dmg) |
| macOS Apple Silicon | [vlc-3.0.21-arm64.dmg](https://get.videolan.org/vlc/3.0.21/macosx/vlc-3.0.21-arm64.dmg) |
| Android | [Google Play Store](https://play.google.com/store/apps/details?id=org.videolan.vlc) |

### ⚖️ Licenciamento

- **VLC**: GPLv2 (ou posterior). Em algumas plataformas, é de facto GPLv3 devido às licenças das dependências.
- **libVLC**: LGPLv2 (ou posterior), permitindo uso em aplicações de terceiros com outras licenças.

### 🛠️ Linguagens de Programação

O desenvolvimento principal do VLC é feito em:
- **C** (principal)
- **C++**
- **Objective-C**
- **Assembly**
- **Rust**

Repositórios relacionados usam outras linguagens:
- **Kotlin/Java** - [VLC para Android](https://code.videolan.org/videolan/vlc-android/)
- **Swift** - [VLC para iOS](https://code.videolan.org/videolan/vlc-ios/)
- **C#** - [LibVLCSharp](https://code.videolan.org/videolan/libvlcsharp/)

---

## libVLC - Engine de Multimídia

### 📖 Visão Geral

A **libVLC** é o core engine e a interface para o framework multimídia no qual o VLC media player é baseado. É uma biblioteca modularizada em **centenas de plugins** que podem ser carregados em tempo de execução.

### ✨ Recursos

- ✅ Reproduz todos os formatos de mídia, codecs e protocolos de streaming
- ✅ Roda em todas as plataformas: desktop, mobile e TVs
- ✅ Decodificação eficiente por hardware, até 8K
- ✅ Navegação em sistemas de arquivos remotos (SMB, FTP, SFTP, NFS)
- ✅ Suporte a servidores UPnP e DLNA
- ✅ Reprodução de CD de áudio, DVD e Blu-ray com navegação por menu
- ✅ Suporte a HDR com tone-mapping para streams SDR
- ✅ Audio passthrough via SPDIF e HDMI (DD+, TrueHD, DTS-HD)
- ✅ Filtros de vídeo e áudio
- ✅ Reprodução de vídeo 360° e áudio 3D (Ambisonics)
- ✅ Cast para Chromecast e renderizadores UPnP

### 📋 Informações Técnicas

| Característica | Valor |
|---------------|-------|
| **Licença** | LGPL 2.1 |
| **Linguagem** | C |
| **Versão Estável** | 3.x |
| **Versão de Desenvolvimento** | 4.x |

### 🔌 Bindings Oficiais (VideoLAN)

| Binding | Linguagem | Plataforma | Repositório |
|---------|-----------|------------|-------------|
| libvlcpp | C++ | Multiplataforma | [code.videolan.org](https://code.videolan.org/videolan/libvlcpp) |
| VLCKit | Objective-C/Swift | Apple (iOS, macOS, tvOS) | [code.videolan.org](https://code.videolan.org/videolan/VLCKit) |
| libvlcjni | Java/Kotlin | Android | [code.videolan.org](https://code.videolan.org/videolan/vlc-android/-/tree/master/libvlc) |
| LibVLCSharp | .NET/Mono (C#) | Multiplataforma | [code.videolan.org](https://code.videolan.org/videolan/LibVLCSharp) |

### 🔌 Bindings da Comunidade

| Binding | Linguagem | Repositório |
|---------|-----------|-------------|
| vlcj | Java (Desktop) | [github.com/caprica/vlcj](https://github.com/caprica/vlcj) |
| python-vlc | Python | [github.com/oaubert/python-vlc](https://github.com/oaubert/python-vlc) |
| vlc-rs | Rust | [github.com/garkimasera/vlc-rs](https://github.com/garkimasera/vlc-rs) |
| libvlc-go | Go | [github.com/adrg/libvlc-go](https://github.com/adrg/libvlc-go) |

### 📚 Exemplos e Amostras

- [LibVLCSharp samples](https://code.videolan.org/mfkl/libvlcsharp-samples)
- [vlcj examples](https://github.com/caprica/vlcj-examples/tree/master/src/main/java/uk/co/caprica/vlcj/test)
- [libvlcpp tests](https://code.videolan.org/videolan/libvlcpp/-/blob/master/test/main.cpp)
- [VLCKit Examples](https://code.videolan.org/videolan/VLCKit/-/tree/master/Examples)
- [libvlcjni samples](https://code.videolan.org/videolan/libvlc-android-samples)
- [python-vlc examples](https://github.com/oaubert/python-vlc/tree/master/examples)

### 📕 Ebook

**"The Good Parts of LibVLC"** é o primeiro livro sobre LibVLC e a comunidade VideoLAN. Apresenta a organização VideoLAN e explora em profundidade a biblioteca nativa LibVLC. Publicado em setembro de 2022.

- [Adquirir Ebook](https://mfkl.gumroad.com/l/libvlc-good-parts)

---

## VLC for Unity

### 📖 Visão Geral

O **vlc-unity** é uma integração da engine LibVLC com o motor de jogos Unity 3D, permitindo incorporar o LibVLC em jogos baseados em Unity.

### 🛠️ Arquitetura

- **Scripting**: Usa [LibVLCSharp](https://code.videolan.org/videolan/LibVLCSharp) (C#)
- **Performance**: Código do plugin escrito em C++ para máximo desempenho
- **APIs Gráficas**: OpenGL, Direct3D, Metal

### 💻 Plataformas Suportadas

| Plataforma | Sistema Mínimo | ABI | API Gráfica |
|------------|----------------|-----|-------------|
| Windows Classic | Windows 7 | x64 | Direct3D 11 |
| Windows UWP | Windows 10 | x64, ARM64 | Direct3D 11 |
| Android | Android 4.2 (API 17) | armeabi-v7a, arm64-v8a, x86, x86_64 | OpenGL ES 2/3 |
| iOS | iOS 9 | ARM64 | Metal |
| macOS | macOS 10.11 | Intel x64, Apple Silicon ARM64 | Metal |

### 🎬 Cenas de Exemplo

- Exemplo mínimo de reprodução com botões
- Reprodução 360° com navegação por teclado
- Vídeo com legendas
- VLCPlayerExample com controles avançados
- Cena 3D de cinema com tela e cadeiras

### 📦 Repositório

- [GitLab: vlc-unity](https://code.videolan.org/videolan/vlc-unity)

---

## Bibliotecas de Decodificação

### libdvdcss

#### 📖 Visão Geral

A **libdvdcss** é uma biblioteca simples projetada para acessar DVDs como um dispositivo de bloco sem se preocupar com descriptografia.

#### ✨ Características

- **Portabilidade**: GNU/Linux, FreeBSD, NetBSD, OpenBSD, Haiku, Mac OS X, Solaris, QNX, OS/2, Windows NT 4.0 SP4+
- **Simplicidade**: Um player de DVD pode ser construído com apenas 4-5 chamadas de API
- **Liberdade**: Licenciada sob GNU GPL
- **Sem região**: Não requer configuração de região do drive

#### 📥 Instalação

**Versão Atual: 1.5.0**

**Debian/Ubuntu:**
```bash
sudo apt install libdvd-pkg
sudo dpkg-reconfigure libdvd-pkg
```

**Git:**
```bash
git clone https://code.videolan.org/videolan/libdvdcss.git
```

**Downloads:** [Releases](https://download.videolan.org/pub/libdvdcss/)

---

### libdvdnav & libdvdread

#### 📖 Visão Geral

A **libdvdnav** é uma biblioteca para desenvolvedores de aplicações multimídia que permite uso fácil de recursos sofisticados de navegação em DVD:

- Menus de DVD
- Reprodução multi-ângulo
- Jogos interativos de DVD

A biblioteca fornece a reprodução do DVD como um único stream lógico de blocos, intercalado por eventos especiais `dvdnav` para reportar certas condições.

#### 📥 Instalação

**Versão Atual: 7.0.0**

**Git:**
```bash
git clone https://code.videolan.org/videolan/libdvdnav.git
```

**Downloads:** [Releases](https://download.videolan.org/pub/videolan/libdvdnav/)

---

### libbluray

#### 📖 Visão Geral

A **libbluray** é uma biblioteca open-source projetada para reprodução de discos Blu-Ray em media players como VLC ou MPlayer.

Este projeto de pesquisa é desenvolvido por uma equipe internacional de desenvolvedores do [Doom9](https://www.doom9.org/).

#### ✨ Características

- **Portabilidade**: GNU/Linux, Windows, MacOS X
- **Licença**: LGPL (software livre)
- **Recursos**: Navegação, parsing de playlist, menus e BD-J
- **Legal**: Livre de circumvenção de DRM, seguro para integração

> **Nota**: A maioria dos Blu-Rays comerciais são protegidos por AACS ou BD+. Esta biblioteca sozinha não é suficiente para reproduzi-los.

#### 📦 Bibliotecas Relacionadas

- [libaacs](https://www.videolan.org/developers/libaacs.html) - Para tecnologias AACS
- [libbdplus](https://www.videolan.org/developers/libbdplus.html) - Para tecnologias BD+

#### 📥 Instalação

**Versão Atual: 1.4.0**

**Download:** [libbluray-1.4.0.tar.xz](https://download.videolan.org/pub/videolan/libbluray/1.4.0/libbluray-1.4.0.tar.xz)

**Git:**
```bash
git clone https://code.videolan.org/videolan/libbluray.git
```

**Mailing List:** [libbluray-devel](https://mailman.videolan.org/listinfo/libbluray-devel)

---

### libdca

#### 📖 Visão Geral

A **libdca** é uma biblioteca livre para decodificação de streams DTS Coherent Acoustics. O código foi escrito por Gildas Bazin e baseado no projeto [a52dec](https://liba52.sourceforge.net/).

**Licença:** GPL

**Padrão:** ETSI 102 114 v1.2.1 (DTS Coherent Acoustics)

#### 🔧 Status de Desenvolvimento

- Implementação do core da especificação em andamento
- Algumas funcionalidades ainda faltando (Joint channels coding, Dynamic range)
- Extensões (canais extra, sample rates 96/192kHz) não implementadas

#### 📦 Projetos que Usam libdca

- VLC media player
- Media Player Classic
- Xine
- FFmpeg
- MPlayer
- ffdshow

#### 📥 Instalação

**Versão Atual: 0.0.6**

**Download:** [libdca-0.0.6.tar.bz2](https://download.videolan.org/pub/videolan/libdca/0.0.6/libdca-0.0.6.tar.bz2)

**Git:**
```bash
git clone https://code.videolan.org/videolan/libdca
```

---

## Bibliotecas de Streaming

### libdvbpsi

#### 📖 Visão Geral

A **libdvbpsi** é uma biblioteca simples projetada para decodificação e geração de tabelas MPEG TS e DVB PSI de acordo com os padrões ISO/IEC 13818 e ITU-T H.222.0.

#### ✨ Recursos

**Tabelas Suportadas (decodificador e gerador):**
- Bouquet Association Table (BAT)
- Conditional Access Table (CAT)
- EPG Information Table (EIT)
- Network Information Table (NIT)
- Program Association Table (PAT)
- Program Map Table (PMT)
- Section Description Table (SDT)
- Splice Information Section Table (SIS)
- TOT Table (TOT)

**Descritores:**
- Todos os descritores MPEG 2
- Decodificadores ATSC EIT, ETT, MGT, STT e VCT

**Plataformas:** GNU/Linux, *BSD, Windows, MacOS X

#### ⚖️ Licenciamento

| Versão | Licença |
|--------|---------|
| 0.2.0+ | LGPL v2.1 |
| < 0.2.0 | GPLv2 |

#### 📥 Instalação

**Versão Atual: 1.3.3** (LGPL v2.1)

**Git:**
```bash
git clone https://code.videolan.org/videolan/libdvbpsi.git
```

Para versão estável:
```bash
git checkout -t origin/branch/1.3.0-bugfix
```

**Downloads:** [Releases](https://download.videolan.org/pub/libdvbpsi/)

---

### biTStream

#### 📖 Visão Geral

O **biTStream** é um conjunto de headers C para acesso simplificado a estruturas binárias especificadas por MPEG, DVB, IETF, SMPTE, IEEE, SCTE, etc.

#### 🔄 biTStream vs. libdvbpsi

| Característica | biTStream | libdvbpsi |
|---------------|-----------|-----------|
| Nível | Mais baixo | Mais alto |
| Eficiência | Menos alocações de memória | Usa estruturas C |
| Cópias | Menos cópias de memória | Mais cópias |
| Separação | Melhor separação entre camadas | Listas encadeadas |

#### ✨ Especificações Implementadas

- ISO/IEC 13818-1, 13818-2, 13818-3 (MPEG-2)
- ISO/IEC 14496-3, 14496-10 (MPEG-4)
- ITU-T H.265 (HEVC)
- ATSC A/52
- ETSI EN 300 468, EN 50 221, TS 103 194
- IETF RFC 3550, RFC 2250, RFC 3611
- SMPTE 2022-1, 2022-6, 291, 352, 337
- IEEE 802.3
- SCTE-35, SCTE-104

**Licença:** MIT

#### 📥 Instalação

**Versão Atual: 1.6**

**Download:** [biTStream 1.6](https://get.videolan.org/bitstream/1.6/)

**Git:**
```bash
git clone https://code.videolan.org/videolan/bitstream.git
```

---

## Ferramentas de Streaming

### DVBlast

#### 📖 Visão Geral

O **DVBlast** é um demuxer e aplicação de streaming MPEG-2/TS simples e poderoso. É escrito para ser o core de um IRD, CID ou gateway ASI customizado, baseado em PC com uma placa suportada por Linux.

#### ✨ Características

- 🎯 Programa leve para condições extremas de memória e CPU
- 📦 Uma dependência runtime (libev), uma dependência de build (biTStream)
- 📺 Suporte a menus CAM (MMI) via aplicação externa
- 🔄 Recarregamento de configuração sem perder pacotes
- 📡 Suporte ao novo S2API do linux-dvb
- 🌐 Suporte a redes IPv6
- 📤 Saída UDP ou RTP para IPTV STBs
- 🔓 Código Aberto: GPLv2

#### 📥 Entradas Suportadas

- Placas linux-dvb (DVB-S, DVB-S2, DVB-C, DVB-T) com ou sem CI
- Placas DVB-ASI (Computer Modules, Deltacast)
- UDP ou RTP (unicast ou multicast) com transport stream

#### 📤 Saídas

- Streams RTP com transport streams
- Filtragem PID por hardware ou software
- Demultiplexing baseado em PID ou serviço
- Descrambling opcional via CAM
- Remapeamento opcional de PID e SID

#### 📥 Instalação

**Versão Atual: 3.5**

**Download:** [dvblast-3.5.tar.bz2](https://get.videolan.org/dvblast/3.5/dvblast-3.5.tar.bz2) (86 KiB)

**Plataformas:** Linux, macOS (com recursos limitados)

**Mailing List:** [dvblast-devel](https://www.videolan.org/developers/lists.html)

---

### Multicat

#### 📖 Visão Geral

O **Multicat** é um conjunto de ferramentas projetadas para manipular facilmente e eficientemente streams multicast em geral, e MPEG-2 Transport Streams em particular.

**Plataformas:** Linux, FreeBSD, Mac OS X

#### 🔧 Componentes

##### multicat
Aplicação 1 entrada/1 saída. Equivalente multicast do popular `netcat`.

**Entradas/Saídas suportadas:**
- Streams de rede (unicast e multicast)
- Arquivos
- Diretórios
- Dispositivos de caractere
- FIFOs

**Casos de uso típicos:**
- Gravar transport streams ao vivo
- Reproduzir arquivos TS sem modificação
- Gravar stream contínuo em diretório com rotação de arquivos

##### ingests
Aplicação complementar para manipular arquivos TS. Lê valores PCR e constrói o arquivo auxiliar necessário para o multicat.

##### aggregartp & reordertp
- **aggregartp**: Divide um único stream RTP em múltiplos links de contribuição com balanceamento de carga
- **reordertp**: Recebe múltiplas entradas e suaviza para output na ordem correta

##### smooths
Minimiza jitter e atende analisadores IAT. Lê timestamps RTP e aguarda o momento adequado para enviar.

##### multilive
Implementa redundância master/slave estilo VRRP entre dois servidores via endereço multicast.

---

## Codificador de Vídeo

### x264

#### 📖 Visão Geral

O **x264** é uma biblioteca e aplicação de software livre para codificação de streams de vídeo no formato **H.264/MPEG-4 AVC**.

**Licença:** GNU GPL (também disponível sob licença comercial)

#### ✨ Destaques

- 🏆 **Melhor da classe** em performance, compressão e recursos
- ⚡ **Alta performance**: 4+ streams 1080p em tempo real em hardware consumer
- 🎨 **Melhor qualidade**: Otimizações psicovisuais mais avançadas
- 📺 **Ampla adoção**: YouTube, Facebook, Vimeo, Hulu, emissoras de TV

#### 🔧 Recursos do Codificador

| Categoria | Recursos |
|-----------|----------|
| **Transformações** | 8x8 e 4x4 adaptativas espaciais |
| **B-frames** | Posicionamento adaptativo, como referências, ordem arbitrária |
| **Entropia** | CAVLC/CABAC |
| **Matrizes** | Quantização customizada |
| **Intra** | Todos os tipos de macroblocos (16x16, 8x8, 4x4, PCM) |
| **Inter P** | Todas as partições (16x16 até 4x4) |
| **Inter B** | Partições 16x16 até 8x8 (incluindo skip/direct) |
| **Rate control** | CQ, CRF, single/multipass ABR, VBV opcional |
| **Otimizações** | Detecção de cena, modo direto adaptativo, Psy-RD, Psy-trellis |
| **Paralelo** | Encoding em múltiplas CPUs |
| **Especial** | Modo lossless preditivo, interlacing (MBAFF), zonas |

#### 🏅 Prêmios

| Ano | Conquista |
|-----|-----------|
| 2010 | 1º lugar MSU Sixth MPEG-4 AVC/H.264 Comparison (~24% melhor que 2º lugar) |
| 2005 | 1º lugar Doom9's 2005 codec shoot-out |
| 2005 | Empate em 1º lugar MSU Second Annual MPEG-4 AVC/H.264 Comparison |

#### 📥 Instalação

**Download Código-Fonte:** [x264-master.tar.bz2](https://code.videolan.org/videolan/x264/-/archive/master/x264-master.tar.bz2) (~750kB)

**Binários:** [artifacts.videolan.org/x264](https://artifacts.videolan.org/x264/)

#### 📞 Suporte

- **Mailing List:** [x264-devel](https://mailman.videolan.org/listinfo/x264-devel)
- **IRC:** `#x264` e `#x264dev` no Libera.chat
- **Issues:** [Issue Tracker](https://code.videolan.org/videolan/x264/issues)

#### 📄 Licenciamento Comercial

Para uso comercial não-GPL, contate: x264licensing@videolan.org

---

## Documentação para Desenvolvedores

### 📚 Guias Disponíveis

| Documento | Descrição | Link |
|-----------|-----------|------|
| VLC User Guide | Documentação do usuário | [Wiki](https://wiki.videolan.org/Documentation:User_Guide/) |
| Quick Start Guide | Início rápido | [Wiki](https://wiki.videolan.org/Documentation:Quick_start_guide/) |
| Streaming HowTo | Como fazer streaming | [Wiki](https://wiki.videolan.org/Documentation:Streaming_HowTo_New/) |
| Hacker's Guide | Funcionamento interno do VLC | [Wiki](https://wiki.videolan.org/Hacker_Guide/) |
| VLC Modules Index | Índice de módulos | [Wiki](https://wiki.videolan.org/Documentation:Modules/) |

### 🛠️ Recursos para Desenvolvedores

#### Áreas de Contribuição

1. **Lua Scripting**: Service discovery, playlist, metadata fetcher, interface modules, extensões
2. **C/C++ Modules**: Core do VLC e módulos
3. **Design/Documentação**: Design de interfaces, documentação
4. **Ports Mobile**: Android, iOS, WinRT
5. **Web Development**: Interface web do VLC, site VideoLAN
6. **Report Bugs**: Reportar bugs e propor melhorias

#### Links de Desenvolvimento

| Recurso | URL |
|---------|-----|
| GitLab Issues | [code.videolan.org/videolan/vlc/-/issues](https://code.videolan.org/videolan/vlc/-/issues/) |
| Mailing List vlc-devel | [videolan.org/developers/lists.html](https://www.videolan.org/developers/lists.html) |
| Traduções | [videolan.org/developers/i18n](https://www.videolan.org/developers/i18n/) |
| Open Hub Stats | [openhub.net/p/vlc](https://www.openhub.net/p/vlc) |
| Jenkins (CI) | [jenkins.videolan.org](https://jenkins.videolan.org) |
| Nightly Builds | [Wiki](https://wiki.videolan.org/Nightly_build/) |
| Código Doxygen | [developers/vlc/doc/doxygen](https://www.videolan.org/developers/vlc/doc/doxygen/html/) |

#### Guias de Desenvolvimento

- [Getting Started at Coding](https://wiki.videolan.org/Getting_Started_At_Coding/)
- [Get the Source Code](https://wiki.videolan.org/GetTheSource/)
- [Compile VLC](https://wiki.videolan.org/Compile_VLC/)
- [Code Conventions](https://wiki.videolan.org/Code_Conventions/)
- [How to Write a Module](https://wiki.videolan.org/Hacker_Guide/How_To_Write_a_Module/)
- [How VLC Modules Load](https://wiki.videolan.org/Documentation:VLC_Modules_Loading/)

### 🐛 Reportando Bugs

Consulte as [diretrizes de reporte de bugs](https://epirat.videolan.me/devdocs/docs/intro/bugreports) antes de enviar.

### 📖 Guia Git

Para contribuidores, consulte o [Git Guide](https://epirat.videolan.me/devdocs/docs/intro/git).

---

## Links e Recursos

### 🌐 Sites Oficiais

| Recurso | URL |
|---------|-----|
| Site Principal | [videolan.org](https://www.videolan.org) |
| GitHub (Mirror) | [github.com/videolan/vlc](https://github.com/videolan/vlc) |
| GitLab Principal | [code.videolan.org](https://code.videolan.org/) |
| Git Repositories | [git.videolan.org](https://git.videolan.org/) |
| Wiki | [wiki.videolan.org](https://wiki.videolan.org) |

### 📖 Documentação

| Recurso | URL |
|---------|-----|
| User Documentation | [docs.videolan.me/vlc-user](https://docs.videolan.me/vlc-user/en/index.html) |
| Developer Docs | [epirat.videolan.me/devdocs](https://epirat.videolan.me/devdocs/) |
| Wiki Documentation | [wiki.videolan.org/Documentation:Documentation](https://wiki.videolan.org/Documentation:Documentation/) |
| Developers Corner | [wiki.videolan.org/VLC_Developers_Corner](https://wiki.videolan.org/VLC_Developers_Corner/) |

### 📦 Projetos Relacionados

| Projeto | Descrição | Link |
|---------|-----------|------|
| libVLC | Engine de multimídia embarcável | [videolan.org/vlc/libvlc](https://www.videolan.org/vlc/libvlc.html) |
| vlc-unity | Integração com Unity | [videolan.org/developers/unity](https://www.videolan.org/developers/unity.html) |
| VLMC | Editor de vídeo não-linear | [videolan.org/vlmc](https://www.videolan.org/vlmc/) |
| DVBlast | Streamer MPEG-2/TS | [videolan.org/projects/dvblast](https://www.videolan.org/projects/dvblast.html) |
| Multicat | Manipulação de multicast | [videolan.org/projects/multicat](https://www.videolan.org/projects/multicat.html) |
| x264 | Codificador H.264/AVC | [videolan.org/developers/x264](https://www.videolan.org/developers/x264.html) |
| libdvdcss | Acesso a DVD | [videolan.org/developers/libdvdcss](https://www.videolan.org/developers/libdvdcss.html) |
| libdvdnav | Navegação DVD | [videolan.org/developers/libdvdnav](https://www.videolan.org/developers/libdvdnav.html) |
| libdvbpsi | MPEG TS e DVB PSI | [videolan.org/developers/libdvbpsi](https://www.videolan.org/developers/libdvbpsi.html) |
| libbluray | Reprodução Blu-ray | [videolan.org/developers/libbluray](https://www.videolan.org/developers/libbluray.html) |
| libdca | Decodificador DTS | [videolan.org/developers/libdca](https://www.videolan.org/developers/libdca.html) |
| biTStream | Headers C para estruturas binárias | [videolan.org/developers/bitstream](https://www.videolan.org/developers/bitstream.html) |

### 💬 Comunidade

- **IRC**: `#videolan` no [Libera.chat](https://libera.chat)
- **Discord LibVLC**: Servidor da comunidade de bindings LibVLC
- **Mailing Lists**: [videolan.org/developers/lists](https://www.videolan.org/developers/lists.html)

### 🤝 Como Contribuir

- **Código**: C, C++, Obj-C, Rust, Kotlin/Java, Swift, C#
- **Empacotamento**: Windows, macOS, distribuições Linux
- **Documentação**: Escrita técnica
- **Design**: Interfaces de usuário
- **Suporte**: Ajudar outros usuários
- **Comunidade**: Gerenciamento e comunicação
- **Doações**: [videolan.org/contribute](https://www.videolan.org/contribute.html)

---

> **Nota**: O VLC e todos os projetos VideoLAN são desenvolvidos por voluntários. Pull requests no GitHub são ignorados; contribuições devem ser enviadas via Merge Requests no [code.videolan.org](https://code.videolan.org/videolan/vlc).

---

*Esta documentação foi compilada a partir das fontes oficiais do projeto VideoLAN.*
