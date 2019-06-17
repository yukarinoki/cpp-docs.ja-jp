---
title: Visual Studio で C++ の Linux ワークロードをインストールする
description: Visual Studio で C++ の Linux ワークロードをダウンロード、インストール、セットアップする方法について説明します。
ms.date: 06/07/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: af4e3ec0ac21951163e92786555559cd02e8148f
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821582"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>Linux ワークロードのダウンロード、インストール、セットアップ


::: moniker range=">=vs-2017"

Windows で Visual Studio IDE を使用して、Linux 物理コンピューター、仮想マシン、または [Windows Subsystem for Linux](/windows/wsl/about) で実行する C++ プロジェクトを作成、編集、およびデバッグできます。 

Visual Studio プロジェクトに変換しなくても、CMake や他の任意のビルド システムを利用する既存のコード ベースで作業できます。 コード ベースがクロス プラットフォームの場合、Visual Studio 内から Windows と Linux の両方をターゲット設定できます。 たとえば、Visual Studio を使用して、Windows 上のコードを編集、デバッグ、プロファイルしてから、すぐに Linux のプロジェクトにターゲットを変更して、追加のテストを実行できます。 Linux ヘッダー ファイルが、ローカル コンピューターに自動的にコピーされ、そこで Visual Studio がそれらを使用して、IntelliSense の完全なサポート (ステートメント入力候補、定義へ移動など) を提供します。 
 
これらのどのシナリオについても、**C++ による Linux 開発**ワークロードが必要です。 

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 では、ビルドとデバッグに別のターゲットを指定できます。 WSL を対象とする場合、リモート接続を追加したり、SSH を構成する必要はありません。

Visual Studio for Linux のプロジェクトでは、[AddressSanitizer (ASan)](https://github.com/google/sanitizers/wiki/AddressSanitizer) のサポートが統合されています。

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="visual-studio-setup"></a>Visual Studio のセットアップ

1. Windows 検索ボックスに「Visual Studio インストーラー」と入力します。![Windows 検索ボックス](media/visual-studio-installer-search.png)
2. **アプリ**の結果でインストーラーを探し、それをダブルクリックします。 インストーラーが開いたら、 **[変更]** を選択して **[ワークロード]** タブをクリックします。 **[Other toolsets]\(その他のツールセット\)** まで下へスクロールして、 **[C++ による Linux 開発]** ワークロードを選択します。

   ![Visual C++ for Linux Development ワークロード](media/linuxworkload.png)

1. IoT または組み込みのプラットフォームを対象としている場合、 **[C++ による Linux 開発]** の右側にある **[インストールの詳細]** ウィンドウに移動して、 **[オプション コンポーネント]** を展開し、必要なコンポーネントを選択します。 Linux で CMake は既定でサポートされるよう選択されています。

1. **[変更]** をクリックして、インストールを続行します。

## <a name="options-for-creating-a-linux-environment"></a>Linux 環境を作成するためのオプション

Linux マシンがまだない場合は、Azure で Linux 仮想マシンを作成できます。 詳細については、「[クイック スタート: Azure portal で Linux 仮想マシンを作成する](/azure/virtual-machines/linux/quick-create-portal)」を参照してください。

Windows 10 の Windows Subsystem for Linux (WSL) では、お好みの Linux ディストリビューションをインストールして、対象とすることができます。 詳細については、「[Windows Subsystem for Linux Installation Guide for Windows 10](/windows/wsl/install-win10)」 (Windows 10 用の Windows Subsystem for Linux のインストール ガイド) を参照してください。 WSL は便利なコンソール環境ですが、グラフィック アプリケーションには推奨されません。 

::: moniker-end

::: moniker range="vs-2019"

## <a name="linux-setup-ubuntu-on-wsl"></a>Linux のセットアップ: WSL 上の Ubuntu

WSL では、リモート接続は必要はありません。 Intellisense のサポートで Linux のヘッダーを Visual Studio と自動的に同期するには、**zip** と **rsync** が必要です。 必要なアプリケーションがまだない場合は、次の手順でインストールできます。

```bash
sudo g++ gdb make rsync zip
```
::: moniker-end

::: moniker range=">=vs-2017"

## <a name="ubuntu-on-remote-linux-systems"></a>リモートの Linux システム上の Ubuntu

インストール先の Linux システムには、**openssh-server**、**g++** 、**gdb**、**gdbserver** がインストールされていて、ssh デーモンが実行されている必要があります。 Intellisense サポート対応のローカル コンピューターでリモート ヘッダーを自動同期するには、**zip** が必須です。 これらのアプリケーションがまだない場合は、次の手順でインストールできます。

1. Linux コンピューターのシェル プロンプトで次のコマンドを実行します。

   ```bash
   sudo apt-get install openssh-server g++ gdb gdbserver zip
   ```

   sudo コマンドにより、root パスワードの入力を求められる場合があります。  その場合は、入力して続行します。 完了すると、必要なサービスとツールがインストールされます。

1. 次のコマンドを実行し、Linux コンピューターで ssh サービスを実行します。

   ```bash
   sudo service ssh start
   ```
   サービスが開始され、バックグラウンドで実行され、接続を受け付けられる状態になります。

::: moniker-end

::: moniker range="vs-2019"

## <a name="fedora-on-wsl"></a>WSL 上の Fedora

Fedora は、**dnf** パッケージ インストーラーを使用しています。 **g++** 、**gdb**、**rsync** および **zip** をダウンロードするには、次を実行します。

   ```bash
   sudo dnf install gcc-g++ gdb rsync zip
   ```

Intellisense のサポートで Linux のヘッダーを Visual Studio と自動的に同期するには、**zip** と **rsync** が必要です。

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="fedora-on-remote-linux-systems"></a>リモートの Linux システム上の Fedora

Fedora を実行しているターゲット マシンで **dnf** パッケージ インストーラーを使用します。 **openssh-server**、**g++** 、**gdb**、**gdbserver**、および **zip** をダウンロードし、ssh デーモンを再起動するには、次の手順を実行します。

1. Linux コンピューターのシェル プロンプトで次のコマンドを実行します。

   ```bash
   sudo dnf install openssh-server gcc-g++ gdb gdb-gdbserver zip
   ```
   sudo コマンドにより、root パスワードの入力を求められる場合があります。  その場合は、入力して続行します。 完了すると、必要なサービスとツールがインストールされます。

1. 次のコマンドを実行し、Linux コンピューターで ssh サービスを実行します。

   ```bash
   sudo systemctl start sshd
   ```

   サービスが開始され、バックグラウンドで実行され、接続を受け付けられる状態になります。

::: moniker-end

::: moniker range="vs-2015"

Linux での C++ での開発は Visual Studio 2017 以降でサポートされています。

::: moniker-end

## <a name="next-steps"></a>次の手順

これで Linux プロジェクトを作成するか開いて、ターゲット システム上で実行できるように構成する準備が整いました。 詳細については次を参照してください:

- [新しい Linux プロジェクトを作成する](create-a-new-linux-project.md)
- [Linux CMake プロジェクトを構成する](cmake-linux-project.md)
