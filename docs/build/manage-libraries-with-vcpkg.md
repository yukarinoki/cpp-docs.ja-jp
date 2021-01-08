---
title: vcpkg を使用してライブラリを管理する
description: Windows、macOS、Linux 上で vcpkg を使用してライブラリを管理する方法について説明します。
ms.date: 12/11/2020
ms.technology: cpp-ide
ms.openlocfilehash: 88f8bc1cff7b4b04f5e38b5018676e313383733f
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684122"
---
# <a name="manage-libraries-with-vcpkg"></a>vcpkg を使用してライブラリを管理する

[vcpkg をインストールする](install-vcpkg.md)と、それを使用してローカル マシン上でライブラリを取得し、構築することができます。

## <a name="search-the-list-of-available-libraries"></a>入手可能なライブラリのリストを検索する

### <a name="windows"></a>[Windows](#tab/windows)

入手可能なパッケージを確認するには、コマンド プロンプトで **`vcpkg search`** を入力します。

このコマンドを使用すると、 *`vcpkg/ports`* サブフォルダー内のコントロール ファイルが列挙されます。 リストは以下のようになります。

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

**`vcpkg search ta`** などのパターンでフィルター処理できます。

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-local-machine"></a>ローカル コンピューターにライブラリをインストールする

**`vcpkg search`** を使用してライブラリの名前を取得したら、 **`vcpkg install`** を使用してライブラリをダウンロードしてからコンパイルします。 vcpkg では、*ports* ディレクトリ内にあるライブラリの portfile を使用します。 トリプレットが指定されていない場合は、vcpkg によってターゲット プラットフォームの既定のトリプレット (x86-windows、x64-linux.cmake、または x64-osx.cmake) がインストールされ、コンパイルされます。

Linux ライブラリの場合、vcpkg はローカル コンピューターにインストールされている gcc に依存します。 macOS では、vcpkg は Clang を使用します。

portfile で依存関係が指定されている場合、vcpkg ではそれらもダウンロードしてインストールします。 ダウンロードの後、vcpkg はライブラリで使用されるのと同じビルド システムを使用して、ライブラリをビルドします。 CMake および (Windows 上の) MSBuild プロジェクト ファイルが優先されますが、MAKE は他のビルド システムと共にサポートされます。 vcpkg がローカル コンピューターで指定されたビルド システムを見つけられない場合、それをダウンロードし、インストールします。

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

CMake プロジェクトの場合は、`CMAKE_TOOLCHAIN_FILE` を使用して、ライブラリを `find_package()` で使用できるようにします。 たとえば、Linux または macOS の場合は次のようになります。

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake
```

Windows の場合:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg\scripts\buildsystems\vcpkg.cmake
```

一部のライブラリには、インストール可能なオプションが含まれています。 たとえば、curl ライブラリを検索すると、サポートされているオプションの一覧が角かっこで囲まれて表示されます。

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

この場合、角かっこ **`[`** および **`]`** は、メタ文字ではなく、リテラルです。

コマンド ラインにインストールする特定のオプションを指定できます。 たとえば、Windows 用の既定の SSL バックエンドを使用して curl 用のライブラリをインストールするには、 **`vcpkg install curl[ssl]:x86-windows`** コマンドを使用します。 このコマンドを実行すると、必要な前提条件がすべてインストールされます。コア ライブラリも、必要に応じてインストールされます。

```cmd
> vcpkg list
curl:x86-windows            7.68.0-3   A library for transferring data with URLs
curl[non-http]:x86-windows             Enables protocols beyond HTTP/HTTPS/HTTP2
curl[ssl]:x86-windows                  Default SSL backend
curl[sspi]:x86-windows                 SSPI support
curl[winssl]:x86-windows               SSL support (Secure Channel / "WinSSL")
zlib:x86-windows            1.2.11-6   A compression library
```

### <a name="macos"></a>[macOS](#tab/macos)

使用できるパッケージを確認するには、vcpkg ルート ディレクトリに移動し、ターミナルで **`./vcpkg search`** と入力します。

このコマンドを使用すると、 *`vcpkg/ports`* サブフォルダー内のコントロール ファイルが列挙されます。 リストは以下のようになります。

```Terminal
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

**`vcpkg search ta`** などのパターンでフィルター処理できます。

```Terminal
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-computer"></a>コンピューターにライブラリをインストールする

**`vcpkg search`** を使用してライブラリの名前を取得したら、 **`vcpkg install`** を使用してライブラリをダウンロードしてからコンパイルします。 vcpkg では、*ports* ディレクトリ内にあるライブラリの portfile を使用します。 トリプレットが指定されていない場合は、vcpkg によってターゲット プラットフォームの既定のトリプレット (x86-windows、x64-linux.cmake、または x64-osx.cmake) がインストールされ、コンパイルされます。

Linux ライブラリの場合、vcpkg はローカル コンピューターにインストールされている gcc に依存します。 macOS では、vcpkg は Clang を使用します。

portfile で依存関係が指定されている場合、vcpkg ではそれらもダウンロードしてインストールします。 ダウンロードの後、vcpkg はライブラリで使用されるのと同じビルド システムを使用して、ライブラリをビルドします。 CMake および (Windows 上の) MSBuild プロジェクト ファイルが優先されますが、MAKE は他のビルド システムと共にサポートされます。 vcpkg がローカル コンピューターで指定されたビルド システムを見つけられない場合、それをダウンロードし、インストールします。

```Terminal
$ ./vcpkg install boost

The following packages will be built and installed:
    boost:x86-macos
  * bzip2:x86-macos
  * zlib:x86-macos
Additional packages (*) will be installed to complete this operation.
```

CMake プロジェクトの場合は、`CMAKE_TOOLCHAIN_FILE` を使用して、ライブラリを `find_package()` で使用できるようにします。 例:

```Terminal
cmake .. -DCMAKE_TOOLCHAIN_FILE=./vcpkg/scripts/buildsystems/vcpkg.cmake
```

一部のライブラリには、インストール可能なオプションが含まれています。 たとえば、curl ライブラリを検索すると、サポートされているオプションの一覧が角かっこで囲まれて表示されます。

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

この場合、角かっこ **`[`** および **`]`** は、メタ文字ではなく、リテラルです。

コマンド ラインにインストールする特定のオプションを指定できます。 たとえば、既定の SSL バックエンドを使用して curl 用のライブラリをインストールするには、 **`./vcpkg install curl[ssl]`** コマンドを使用します。 このコマンドを実行すると、必要な前提条件がすべてインストールされます。コア ライブラリも、必要に応じてインストールされます。

### <a name="linux"></a>[Linux](#tab/linux)

使用できるパッケージを確認するには、シェルで vcpkg ルート ディレクトリに移動し、 **`./vcpkg search`** と入力します。

このコマンドを使用すると、 *`vcpkg/ports`* サブフォルダー内のコントロール ファイルが列挙されます。 リストは以下のようになります。

```shell
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

**`./vcpkg search ta`** などのパターンでフィルター処理できます。

```shell
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-linux-machine"></a>Linux マシンにライブラリをインストールする

**`./vcpkg search`** を使用してライブラリの名前を取得したら、 **`/vcpkg install`** を使用してライブラリをダウンロードしてからコンパイルします。 vcpkg には、 *`ports`* ディレクトリ内にあるライブラリの portfile が使用されます。 トリプレットが指定されていない場合は、vcpkg によってターゲット プラットフォームの既定のトリプレット (x64-linux.cmake など) がインストールされ、コンパイルされます。

Linux ライブラリの場合、vcpkg はローカル コンピューターにインストールされている gcc に依存します。

portfile で依存関係が指定されている場合、vcpkg ではそれらもダウンロードしてインストールします。 ダウンロードの後、vcpkg はライブラリで使用されるのと同じビルド システムを使用して、ライブラリをビルドします。 CMake プロジェクトが優先されますが、他のビルド システムと共に MAKE がサポートされます。 vcpkg がローカル コンピューターで指定されたビルド システムを見つけられない場合、それをダウンロードし、インストールします。

```shell
$ ./vcpkg install boost:x64-linux

The following packages will be built and installed:
    boost:x64-linux
  * bzip2:x64-linux
  * zlib:x64-linux
Additional packages (*) will be installed to complete this operation.
```

CMake プロジェクトの場合は、`CMAKE_TOOLCHAIN_FILE` を使用して、ライブラリを `find_package()` で使用できるようにします。 例:

```shell
cmake .. -DCMAKE_TOOLCHAIN_FILE=./vcpkg/scripts/buildsystems/vcpkg.cmake
```

一部のライブラリには、インストール可能なオプションが含まれています。 たとえば、curl ライブラリを検索すると、サポートされているオプションの一覧が角かっこで囲まれて表示されます。

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

この場合、角かっこ **`[`** および **`]`** は、メタ文字ではなく、リテラルです。

コマンド ラインにインストールする特定のオプションを指定できます。 たとえば、既定の SSL バックエンドを使用して curl 用のライブラリをインストールするには、 **`./vcpkg install curl[ssl]`** コマンドを使用します。 このコマンドを実行すると、必要な前提条件がすべてインストールされます。コア ライブラリも、必要に応じてインストールされます。

---

## <a name="list-the-libraries-already-installed"></a>既にインストールされているライブラリをリストする

いくつかのライブラリをインストールした後、Windows 上で **`vcpkg list`** コマンドを使用して、ライブラリを確認することができます。 Linux と macOS のコマンドは似ています。

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

## <a name="target-linux-from-windows-via-wsl"></a>WSL 経由で Windows から Linux をターゲットにする

Linux 用 Windows サブシステム (WSL) を使用すると、Windows コンピューターから Linux バイナリを生成できます。 指示に従って、[Windows 10 で WSL を設定](/windows/wsl/install-win10)します。 次に、[Linux 用の Visual Studio 拡張機能](https://devblogs.microsoft.com/cppblog/targeting-windows-subsystem-for-linux-from-visual-studio/)を使用して構成します。 Windows と Linux のすべてのビルド済みのライブラリは同じフォルダーに配置できます。 これらは、Windows と WSL の両方からアクセスできます。

## <a name="export-compiled-binaries-and-headers"></a><a name="export_binaries_per_project"></a> コンパイル済みのバイナリとヘッダーをエクスポートする

チームのすべてのユーザーが同じライブラリをダウンロードしてビルドすることは、効率的ではありません。 1 人のチーム メンバーが **`vcpkg export`** コマンドを使用して、バイナリとヘッダー、または NuGet パッケージの共用の zip ファイルを作成します。 その後、他のチーム メンバーと共有すると簡単です。

## <a name="updateupgrade-installed-libraries"></a>インストールされているライブラリを更新/アップグレードする

パブリック カタログは、ライブラリの最新バージョンで最新の状態に保たれます。 古いローカル ライブラリを特定するには、 **`vcpkg update`** を使用します。 ポート コレクションをパブリック カタログの最新バージョンに更新する準備ができたら、 **`vcpkg upgrade`** コマンドを実行します。 これでは、インストールされている古いライブラリが自動的にダウンロードされ、再構築されます。

既定では、 **`vcpkg upgrade`** コマンドを実行すると、古いライブラリがリストされるのみであり、アップグレードは行われません。 実際にライブラリをアップグレードするには、 **`--no-dry-run`** オプションを使用します。

```cmd
> vcpkg upgrade --no-dry-run
```

### <a name="upgrade-options"></a>アップグレード オプション

- **`--no-dry-run`**  アップグレードを実行します。このオプションが指定されていない場合、コマンドを実行しても、古いパッケージがリストされるのみとなります。
- **`--keep-going`**  パッケージのいずれかがインストールに失敗した場合でも、インストールを続行します。
- **`--triplet <t>`**  修飾されていないパッケージに既定のトリプレットを設定します。
- **`--vcpkg-root <path>`**  現在のディレクトリまたはツール ディレクトリではなく、使用する vcpkg ディレクトリを指定します。

### <a name="upgrade-example"></a>アップグレードの例

次の例は、Windows 上で指定したライブラリのみをアップグレードする方法を示します。 Linux と macOS のコマンドは似ています。 vcpgk は必要に応じて依存関係を自動的に取得します。

```cmd
c:\users\username\vcpkg> vcpkg upgrade tiny-dnn:x86-windows zlib
The following packages are up-to-date:
   tiny-dnn:x86-windows

The following packages will be rebuilt:
    * libpng[core]:x86-windows
    * tiff[core]:x86-windows
      zlib[core]:x86-windows
Additional packages (*) will be modified to complete this operation.
If you are sure you want to rebuild the above packages, run this command with the --no-dry-run option.
```

## <a name="contribute-new-libraries"></a>新しいライブラリを投稿する

プライベート ポート コレクションに好きなライブラリを含めることができます。 パブリック カタログ用の新しいライブラリを提案するには、[GitHub vcpkg の issue ページ](https://github.com/Microsoft/vcpkg/issues)で案件を開きます。

## <a name="remove-a-library"></a>ライブラリを削除する

**`vcpkg remove`** を入力して、インストールされているライブラリを削除します。 他のライブラリがそれに依存している場合は、 **`--recurse`** を指定してコマンドを再実行するよう求められます。実行すると、すべてのダウンストリーム ライブラリが削除されます。

## <a name="see-also"></a>関連項目

[vcpkg: Windows、Linux、および macOS 用の C++ パッケージ マネージャー](./vcpkg.md)\
[GitHub 上の vcpkg](https://github.com/Microsoft/vcpkg)\
[vcpkg をインストールする](install-vcpkg.md)\
[vcpkg を統合する](integrate-vcpkg.md)\
[vcpkg コマンドライン リファレンス](vcpkg-command-line-reference.md)\
[クイック スタート](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[よく寄せられる質問](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)\
[パッケージのインストールと使用の例: SQLite](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md)
