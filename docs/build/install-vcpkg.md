---
title: vcpkg を Windows、Linux、macOS にインストールする
description: vcpkg を Windows、Linux、macOS にインストールして更新する方法について説明します。
ms.date: 12/17/2020
ms.topic: reference
ms.technology: cpp-ide
ms.openlocfilehash: b508134693d5687898f0e5202f54ee35b91680bb
ms.sourcegitcommit: 977b5151e7dae7584112328bab515fb15622a6cc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "104883858"
---
# <a name="install-vcpkg-on-windows-linux-and-macos"></a>vcpkg を Windows、Linux、macOS にインストールする

vcpkg は、vcpkg GitHub リポジトリからローカルに複製 (コピー) を作成してインストールします。

## <a name="install-vcpkg"></a>vcpkg をインストールする

具体的な方法については、お使いのプラットフォームを選択してください。

### <a name="linux"></a>[Linux](#tab/linux)

Linux の前提条件:

- [Git](https://git-scm.com/downloads)
- g++ バージョン 6 以降

#### <a name="to-install-linux-development-tools"></a>Linux の開発ツールをインストールするには

Linux ディストリビューションが異なる場合、別のパッケージのインストールが必要な場合があります。 Debian、Ubuntu、popOS およびその他の Debian ベースのディストリビューションでは、次の手順に従います。

1. シェル ウィンドウで次のコマンドを実行します。

   **`sudo apt-get update`**

1. 更新が完了したら、次のコマンドを実行します。

   **`sudo apt-get install build-essential tar curl zip unzip`**

CentOS では、次の手順に従います。

1. シェル ウィンドウで次のコマンドを実行します。

   **`sudo yum install centos-release-scl`**

1. 次いで、次のコマンドを実行して開発ツールをインストールして有効にします。

   **`sudo yum install devtoolset-7`**

   **`scl enable devtoolset-7 bash`**

その他のディストリビューションでは、必ず g++ 6 以降をインストールするようにしてください。

#### <a name="to-copy-and-set-up-vcpkg-on-linux"></a>Linux に vcpkg をコピーおよび設定するには

1. シェル ウィンドウで vcpkg の複製した自分のインスタンス用にディレクトリを作成します。 異なるビルド ターゲットにライブラリをインストールする場合、ディレクトリ名にターゲットを含めることが推奨されます。 一部のポート ビルド システムでパスの問題が発生するおそれがあるため、 *`./x64`* や *`./iot`* などの空白のない短いパス名をお勧めします。 シェル ウィンドウで今作成したディレクトリに移動します。

1. vcpkg リポジトリを GitHub から 複製します ([https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg))。

   > **`git clone https://github.com/microsoft/vcpkg`**

   このコマンドにより *`vcpkg`* サブディレクトリにリポジトリのローカル コピーが作成されます。 この場所は、この vcpkg の複製の vcpkg "*ルート ディレクトリ*" です。

1. 次いで vcpkg のルート ディレクトリに移動し、vcpkg のブートストラップ コマンドを実行します。

   > **`./bootstrap-vcpkg.sh`**

   ブートストラップによって、コンパイラの場所、ツールおよび標準のライブラリを使用して vcpkg が構成されます。

### <a name="macos"></a>[macOS](#tab/macos)

macOS の前提条件:

- macOS の開発ツール
- macOS 10.14 以前の場合は、次も必要です。
  - Homebrew
  - g++ バージョン 6 以降

#### <a name="to-install-macos-developer-tools"></a>macOS の開発ツールをインストールするには

1. macOS 10.15 のターミナルで次のコマンドを実行します。

   **`xcode-select --install`**

   次いでウィンドウに表示されるプロンプトに従います。

macOS 10.14 以前の場合、homebrew から g++ をインストールする必要もあります。 この手順は、10.15 以前の macOS を使用しているときのみ必要です。

#### <a name="to-install-gcc-for-macos-before-1015"></a>10.15 以前の macOS に GCC をインストールするには

1. ターミナルを開き、次のコマンドを実行して、Homebrew をインストールします。

   **`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`**

1. ターミナルで次のコマンドを実行し、gcc の最新バージョンをインストールします。

   **`brew install gcc`**

#### <a name="to-copy-and-set-up-vcpkg-on-macos"></a>macOS に vcpkg を複製して設定するには

1. ターミナルで vcpkg の複製した自分のインスタンス用にディレクトリを作成します。 異なるビルド ターゲットにライブラリをインストールする場合、ディレクトリ名にターゲットを含めることが推奨されます。 一部のポート ビルド システムでパスの問題が発生するおそれがあるため、 *`./macos`* や *`./iot`* などの空白のない短いパス名をお勧めします。 ターミナルで今作成したディレクトリに移動します。

1. vcpkg リポジトリを GitHub から 複製します ([https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg))。

   > **`git clone https://github.com/microsoft/vcpkg`**

   このコマンドにより *`vcpkg`* サブディレクトリにリポジトリのローカル コピーが作成されます。 この場所は、この vcpkg の複製の vcpkg "*ルート ディレクトリ*" です。

1. 次いで vcpkg のルート ディレクトリに移動し、vcpkg のブートストラップ コマンドを実行します。

   > **`./bootstrap-vcpkg.sh`**

   ブートストラップによって、コンパイラの場所、ツールおよび標準のライブラリを使用して vcpkg が構成されます。

### <a name="windows"></a>[Windows](#tab/windows)

前提条件:

- Windows 7 以降
- [Git for Windows](https://git-scm.com/downloads)
- [Visual Studio](https://visualstudio.microsoft.com/) 2015 アップデート 3 以降と英語の言語パック

#### <a name="to-copy-and-set-up-vcpkg-on-windows"></a>Windows に vcpkg を複製して設定するには

1. コマンド プロンプト ウィンドウで vcpkg の複製した自分のインスタンス用にディレクトリを作成します。 異なるビルド ターゲットにライブラリをインストールする場合、ディレクトリ名にターゲットを含めることが推奨されます。 一部のポート ビルド システムでパスの問題が発生するおそれがあるため、 *`C:\src\win32\`* や *`C:\dev\iot\`* などの空白のない短いパス名をお勧めします。 コマンド ウィンドウで今作成したディレクトリに移動します。

1. vcpkg リポジトリを GitHub から 複製します ([https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg))。

   > **`git clone https://github.com/microsoft/vcpkg`**

   このコマンドにより *`vcpkg`* サブディレクトリにリポジトリのローカル コピーが作成されます。 この場所は、この vcpkg の複製の vcpkg "*ルート ディレクトリ*" です。

1. ダウンロードが完了したら、お使いのコマンド プロンプトのウィンドウで *`vcpkg`* ディレクトリに移動します。

1. vcpkg のルート ディレクトリで、vcpkg のブートストラップ コマンドを実行します。

   > **`bootstrap-vcpkg.bat`**

   ブートストラップによって、Microsoft C/C++ のツールの場所、ライブラリおよび Windows SDK を使用して vcpkg が構成されます。

---

vcpkg の設定が完了したら、ライブラリをインストールできます。 詳細については、「[vcpkg を使用してライブラリを管理する](manage-libraries-with-vcpkg.md)」を参照してください。 vcpkg は、Windows 上の Visual Studio または任意のプラットフォームの Visual Studio Code と統合することも可能です。 詳細については、[vcpkg の統合](integrate-vcpkg.md)に関する説明を参照してください。

## <a name="update-vcpkg"></a>vcpkg の更新

Vcpkg パッケージ マネージャーは、GitHub で定期的に更新されます。 vcpkg のクローンを最新バージョンに更新するには、vcpkg ルート ディレクトリから **`git pull`** を実行します。 このコマンドを実行すると、vcpkg のコピーが GitHub でのバージョンと同期されます。 ダウンロードが完了したら、再度ブートストラップを実行します。 ブートストラップによって vcpkg プログラムが再構築されますが、インストールされているライブラリはそのままです。

## <a name="uninstall-vcpkg"></a>vcpkg をアンインストールする

vcpkg をアンインストールするには、単純に *`vcpkg`* ディレクトリを削除します。 このディレクトリを削除すると、vcpkg ディストリビューションと、vcpkg によってインストールされたすべてのライブラリがアンインストールされます。

ただし **`vcpkg integrate install`** を実行した場合は、フォルダーが削除される前に、 **`vcpkg integrate remove`** を実行して、統合がクリーンになっていることを確認する必要があります。 詳細については、[vcpkg の統合](integrate-vcpkg.md)に関する説明を参照してください。

## <a name="see-also"></a>関連項目

[vcpkg: Windows、Linux、および macOS 用の C++ パッケージ マネージャー](./vcpkg.md)\
[GitHub 上の vcpkg](https://github.com/Microsoft/vcpkg)\
[vcpkg を統合する](integrate-vcpkg.md)\
[vcpkg を使用してライブラリを管理する](manage-libraries-with-vcpkg.md)\
[vcpkg コマンドライン リファレンス](vcpkg-command-line-reference.md)\
[クイック スタート](https://github.com/microsoft/vcpkg/blob/master/docs/README.md)\
[よく寄せられる質問](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
