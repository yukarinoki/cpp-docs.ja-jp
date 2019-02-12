---
title: Visual Studio で C++ の Linux ワークロードをインストールする
description: Visual Studio で C++ の Linux ワークロードをダウンロード、インストール、セットアップする方法について説明します。
ms.date: 02/06/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: c01c8ddeeb8439a7610c0f6c7c11b608ab3675d8
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763889"
---
# <a name="download-install-and-setup-the-linux-workload"></a>Linux ワークロードのダウンロード、インストール、セットアップ

Windows で Visual Studio IDE を使用して、Linux 物理コンピューター、仮想マシン、または [Windows Subsystem for Linux](/windows/wsl/about) で実行する C++ プロジェクトを作成、編集、およびデバッグできます。 これらのシナリオのいずれかについては、最初に **C++ による Linux 開発**ワークロードをインストールします。

## <a name="visual-studio-setup"></a>Visual Studio のセットアップ

1. Windows 検索ボックス (![Windows 検索ボックス](media/visual-studio-installer-search.png)) に「Visual Studio インストーラー」と入力します
2. **アプリ**の結果でインストーラーを探し、それをダブルクリックします。 インストーラーが開いたら、**[変更]** を選択して **[ワークロード]** タブをクリックします。**[Other toolsets]\(その他のツールセット\)** まで下へスクロールして、**[C++ による Linux 開発]** ワークロードを選択します。

   ![Visual C++ for Linux Development ワークロード](media/linuxworkload.png)

1. CMake を使用するか、IoT または組み込みのプラットフォームを対象としている場合、**[C++ による Linux 開発]** の右側にある **[インストールの詳細]** ウィンドウに移動して、**[オプション コンポーネント]** を展開し、必要なコンポーネントを選択します。

1. **[変更]** をクリックして、インストールを続行します。

## <a name="options-for-creating-a-linux-environment"></a>Linux 環境を作成するためのオプション

Linux マシンがまだない場合は、Azure で Linux 仮想マシンを作成できます。 詳細については、「[クイック スタート: Azure portal で Linux 仮想マシンを作成する](/azure/virtual-machines/linux/quick-create-portal)」を参照してください。

Windows 10 でのもう 1 つのオプションは、Windows Subsystem for Linux のアクティブ化です。 詳細については、「[Windows 10 Installation Guide](/windows/wsl/install-win10)」(Windows 10 インストール ガイド) を参照してください。

## <a name="linux-setup-ubuntu"></a>Linux のセットアップ: Ubuntu

インストール先の Linux コンピューターには **openssh-server**、**g++**、**gdb**、**gdbserver** がインストールされていて、ssh デーモンが実行している必要があります。 Intellisense サポート対応のローカル コンピューターでリモート ヘッダーを自動同期するには、**zip** が必須です。 これらのアプリケーションがまだない場合は、次の手順でインストールできます。

1. Linux コンピューターのシェル プロンプトで次のコマンドを実行します。

   `sudo apt-get install openssh-server g++ gdb gdbserver zip`

   sudo コマンドにより、root パスワードの入力を求められる場合があります。  その場合は、入力して続行します。 完了すると、必要なサービスとツールがインストールされます。

1. 次のコマンドを実行し、Linux コンピューターで ssh サービスを実行します。

   `sudo service ssh start`

   サービスが開始され、バックグラウンドで実行され、接続を受け付けられる状態になります。

## <a name="linux-setup-fedora"></a>Linux のセットアップ: Fedora

Fedora を実行しているターゲット マシンで **dnf** パッケージ インストーラーを使用します。 **openssh-server**、**g++**、**gdb**、**gdbserver**、および **zip** をダウンロードし、ssh デーモンを再起動するには、次の手順を実行します。

1. Linux コンピューターのシェル プロンプトで次のコマンドを実行します。

   `sudo dnf install openssh-server gcc-g++ gdb gdb-gdbserver zip`

   sudo コマンドにより、root パスワードの入力を求められる場合があります。  その場合は、入力して続行します。 完了すると、必要なサービスとツールがインストールされます。

1. 次のコマンドを実行し、Linux コンピューターで ssh サービスを実行します。

   `sudo systemctl start sshd`

   サービスが開始され、バックグラウンドで実行され、接続を受け付けられる状態になります。

