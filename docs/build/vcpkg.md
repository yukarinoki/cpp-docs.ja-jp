---
title: 'vcpkg: Windows、Linux、および macOS 用の C++ パッケージ マネージャー'
description: vcpkg は、Windows、Linux、および macOS でのオープン ソースの C++ ライブラリの取得およびインストール作業を大幅に簡素化するコマンド ライン パッケージ マネージャーです。
ms.date: 07/06/2020
ms.technology: cpp-ide
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.openlocfilehash: ec908824c19099ad6eaa46a4d85c0187ef12b3fd
ms.sourcegitcommit: 102bd6f7a878d85c8ceab8f28d0359f562850ea0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "96862556"
---
# <a name="vcpkg-a-c-package-manager-for-windows-linux-and-macos"></a>vcpkg: Windows、Linux、および macOS 用の C++ パッケージ マネージャー

vcpkg は、C++ のコマンド ライン パッケージ マネージャーです。 これにより、Windows、Linux、および macOS でのサードパーティ ライブラリの取得とインストール作業を大幅に簡素化できます。 プロジェクトでサードパーティ ライブラリを使用する場合は、vcpkg を使用して、それらをインストールすることをお勧めします。 vcpkg では、オープン ソース ライブラリと専用ライブラリの両方がサポートされています。 vcpkg Windows カタログ内のすべてのライブラリは、Visual Studio 2015、Visual Studio 2017、Visual Studio 2019 との互換性がテストされています。 vcpkg は現在、Windows カタログと Linux/macOS のカタログの間で、1,900 以上のライブラリをサポートしています。 C++ コミュニティでは、両方のカタログに継続的にライブラリが追加されています。

## <a name="simple-yet-flexible"></a>簡単かつ柔軟

単一のコマンドで、ソースをダウンロードして、ライブラリをビルドすることができます。 vcpkg はそれ自体がオープン ソース プロジェクトであり、GitHub で入手できます。 個人で複製した vcpkg は任意の方法でカスタマイズできます。 たとえば、パブリック カタログのとは異なるライブラリを指定したり、別のバージョンのライブラリを指定することができます。 1 台のコンピューターに vcpkg のクローンを複数持つことができます。 それぞれは、独自のコンパイル スイッチを使用して、ライブラリのカスタム コレクションを生成するように設定できます。 各クローンは自己完結型の環境であり、独自の階層でのみ動作する vcpkg.exe の独自のコピーが含まれます。 vcpkg はどの環境変数にも追加されず、Windows レジストリや Visual Studio に依存していません。

## <a name="sources-not-binaries"></a>バイナリではなくソース

vcpkg は Windows カタログ内のライブラリに、バイナリ<sup>1</sup> ではなく、ソースをダウンロードします。 発見できる最新バージョンの Visual Studio を使って、それらのソースをコンパイルします。 C++ では、アプリケーション コードと使用されるすべてのライブラリの両方が、同じバージョンのコンパイラでコンパイルされていることが重要です。 vcpkg を使用すると、バイナリが一致しない可能性と、それによって問題が生じる可能性がなくなるか、大幅に減少します。 特定のバージョンのコンパイラを標準で使用しているチームでは、1 人のチーム メンバーが vcpkg を使用してソースをダウンロードし、一連のバイナリをコンパイルします。 その後、他のチーム メンバー用にエクスポート コマンドを使用してバイナリとヘッダーを圧縮します。 詳細については、以下の「[コンパイル済みのバイナリとヘッダーをエクスポートする](#export_binaries_per_project)」を参照してください。

また、ポートのコレクションにプライベート ライブラリを持つ vcpkg クローンを作成することもできます。 作成済みのバイナリとヘッダーをダウンロードするポートを追加します。 次に、それらのファイルを適切な場所に単にコピーする *portfile.cmake* ファイルを記述します。

<sup>1</sup> *注: 一部の専用のライブラリでは、ソースは入手できません。vcpkg では、このような場合に互換性のあるビルド済みのバイナリをダウンロードします。*

## <a name="installation"></a>インストール

vcpkg リポジトリを GitHub から 複製します ([https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg))。 任意のフォルダーの場所にダウンロードすることができます。 この場所は、vcpkg "*ルート*" です。 ダウンロードが完了したら、コマンド シェルでそのディレクトリに変更します。

vcpkg ルート ディレクトリで、vcpkg ブートストラップを実行します。

- **`bootstrap-vcpkg.bat`** (Windows)
- **`./bootstrap-vcpkg.sh`** (Linux、macOS)

Linux または macOS では、次の例の **`./`** を使用して、vcpkg コマンドにプレフィックスを付ける必要がある場合があります。 これらのコマンドは、必ず vcpkg ルート ディレクトリから実行してください。

## <a name="search-the-list-of-available-libraries"></a>入手可能なライブラリのリストを検索する

入手可能なパッケージを確認するには、コマンド プロンプトで **`vcpkg search`** を入力します。

このコマンドは、*vcpkg/ports* サブフォルダーにあるコントロール ファイルを列挙します。 リストは以下のようになります。

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

## <a name="list-the-libraries-already-installed"></a>既にインストールされているライブラリをリストする

いくつかのライブラリをインストールした後で、 **`vcpkg list`** を使用して、その内容を確認できます。

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

## <a name="integrate-with-visual-studio-windows"></a>Visual Studio (Windows) との統合

### <a name="per-user"></a>ユーザーごと

**`vcpkg integrate install`** を実行して、ユーザーごとにすべての vcpkg ヘッダー ファイルとバイナリを検索するように Visual Studio を構成します。 VC++ のディレクトリ パスを手動で編集する必要はありません。 vcpkg のクローンが複数ある場合、このコマンドを実行するクローンが新しい既定の場所となります。

これで、フォルダー/ヘッダーを入力するだけでヘッダーを #include でインクルードできるようになり、オートコンプリートが支援してくれます。 ライブラリにリンクする場合や、プロジェクト参照を追加する場合は、追加の手順が必要になります。 次の図は、Visual Studio が azure-storage-cpp ヘッダーをどのように検索するかを示しています。 vcpkg は、ターゲット プラットフォームでパーティション分割される、 */installed* サブフォルダーにそのヘッダーを配置します。 以下の図は、ライブラリの */was* サブフォルダーにあるインクルード ファイルのリストを示しています。

![vcpkg と IntelliSense](media/vcpkg-intellisense.png "vcpkg と IntelliSense")

### <a name="per-project"></a>プロジェクトごと

アクティブになっている vcpkg インスタンスのバージョンとは異なる特定のバージョンのライブラリを使用する必要がある場合は、次の手順に従います。

1. vcpkg の新しいクローンを作成します。
1. ライブラリの portfile を変更して、必要なバージョンを取得します。
1. **`vcpkg install <library>`** を実行します。
1. **`vcpkg integrate project`** を使用して、プロジェクトごとにそのライブラリを参照する NuGet パッケージを作成します。

## <a name="integrate-with-visual-studio-code-linuxmacos"></a>Visual Studio Code (Linux/macOS) との統合

**`vcpkg integrate install`** を実行して、Visual Studio Code (Linux/macOS) を構成します。 このコマンドは、vcpkg 登録の場所を設定し、ソース ファイルで IntelliSense を有効にします。

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

次の例では、指定したライブラリのみをアップグレードする方法を示します。 vcpgk は必要に応じて依存関係を自動的に取得します。

```cmd
c:\users\satyan\vcpkg> vcpkg upgrade tiny-dnn:x86-windows zlib
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

## <a name="customize-vcpkg"></a>vcpkg をカスタマイズする

好きなように vcpkg のクローンを変更することができます。 vcpkg のクローンを複数作成し、それぞれの portfile を変更することもできます。 このようにすると、簡単に特定のバージョンのライブラリを取得したり、特定のコマンド ライン パラメーターを指定できます。 たとえば、1 つの企業内にある開発者グループがそれぞれ、そのグループに固有の依存関係を持つソフトウェアで作業しているとします。 この問題は、各チームに vcpkg のクローンを設定することで解決できます。 次に、クローンを変更してライブラリのバージョンをダウンロードし、各チームが必要とするコンパイル スイッチを設定します。

## <a name="update-vcpkg"></a>vcpkg の更新

Vcpkg パッケージ マネージャーは、GitHub で定期的に更新されます。 vcpkg のクローンを最新バージョンに更新するには、vcpkg ルート ディレクトリから **`git pull`** を実行します。 このコマンドを実行すると、vcpkg のコピーが GitHub でのバージョンと同期されます。 ダウンロードが完了したら、再度ブートストラップを実行します。 ブートストラップによって vcpkg プログラムが再構築されますが、インストールされているライブラリはそのままです。

## <a name="uninstall-vcpkg"></a>vcpkg をアンインストールする

vcpkg をアンインストールするには、vcpkg ディレクトリを削除するだけです。 このディレクトリを削除すると、vcpkg ディストリビューションと、vcpkg によってインストールされたすべてのライブラリがアンインストールされます。

ただし **`vcpkg integrate install`** を実行した場合は、フォルダーが削除される前に、 **`vcpkg integrate remove`** を実行して、統合がクリーンになっていることを確認する必要があります。

## <a name="send-feedback-about-vcpkg"></a>vcpkg のフィードバックを送信する

バグ報告や機能の提案など、vcpkg に関するフィードバックを Microsoft に送信するには、 **`vcpkg contact --survey`** コマンドを使用します。

## <a name="the-vcpkg-folder-hierarchy"></a>vcpkg のフォルダー階層

vcpkg のすべての機能とデータは、''インスタンス'' という 1 つのディレクトリ階層内で自己完結しています。 レジストリの設定や環境変数はありません。 1 台のコンピューターで、相互に干渉しない vcpkg のインスタンスはいくつでも使用できます。

vcpkg インスタンスの内容は次のとおりです。

- buildtrees - 各ライブラリの作成元となるソースのサブフォルダーが含まれています。
- docs - ドキュメントと例
- downloads - ダウンロードしたツールまたはソースのキャッシュ コピー。 vcpkg は、インストール コマンドの実行時に最初にここを検索します。
- installed - インストールされている各ライブラリのヘッダーとバイナリが含まれています。 Visual Studio と統合する場合、基本的にこのフォルダーがその検索パスに追加されます。
- packages - インストール間のステージング用の内部フォルダー。
- ports - カタログ内の各ライブラリ、そのバージョン、およびダウンロード場所を記述するファイル。 必要に応じて、独自のポートを追加できます。
- scripts - vcpkg で使用されるスクリプト (CMake、PowerShell)。
- toolsrc - vcpkg および関連するコンポーネントの C++ ソース コード
- triplets - サポートされているターゲット プラットフォーム (x86-windows や x64-uwp など) の設定が含まれます。

## <a name="command-line-reference"></a>コマンド ライン リファレンス

|コマンド|説明|
|---------|---------|
|**`vcpkg search [pat]`**|インストールに使用できるパッケージを検索します|
|**`vcpkg install <pkg>...`**|パッケージをインストールします|
|**`vcpkg remove <pkg>...`**|パッケージをアンインストールします|
|**`vcpkg remove --outdated`**|古いパッケージをアンインストールします|
|**`vcpkg list`**|インストールされているパッケージをリストします|
|**`vcpkg update`**|更新対象のパッケージのリストを表示します|
|**`vcpkg upgrade`**|すべての古いパッケージをリビルドします。|
|**`vcpkg hash <file> [alg]`**|特定のアルゴリズム (既定では SHA512) を使用して、ファイルをハッシュします|
|**`vcpkg integrate install`**|インストールされているパッケージをユーザー全体で使用できるようにします。 初回使用時は管理特権が必要です|
|**`vcpkg integrate remove`**|ユーザー全体の統合を削除します|
|**`vcpkg integrate project`**|個々の VS プロジェクト使用のために参照する NuGet パッケージを生成します|
|**`vcpkg export <pkg>... [opt]...`**|パッケージをエクスポートします|
|**`vcpkg edit <pkg>`**|編集対象のポートを開きます (既定の 'コード' %EDITOR% を使用)|
|**`vcpkg create <pkg> <url> [archivename]`**|新しいパッケージを作成します|
|**`vcpkg cache`**|キャッシュされたコンパイル済みのパッケージをリストします|
|**`vcpkg version`**|バージョン情報を表示します|
|**`vcpkg contact --survey`**|フィードバックを送信する連絡先の情報を表示します。|

### <a name="options"></a>オプション

|オプション|説明|
|---------|---------|
|**`--triplet <t>`**|ターゲット アーキテクチャのトリプレットを指定します。 (既定値: `%VCPKG_DEFAULT_TRIPLET%`。 **`vcpkg help triplet`** も参照してください)|
|**`--vcpkg-root <path>`**|vcpkg ルート ディレクトリを指定します (既定値: `%VCPKG_ROOT%`)|
