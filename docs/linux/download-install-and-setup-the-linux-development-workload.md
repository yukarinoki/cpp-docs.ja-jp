---
title: Visual Studio で C++ の Linux ワークロードをインストールする
description: Visual Studio で C++ の Linux ワークロードをダウンロード、インストール、セットアップする方法について説明します。
ms.date: 03/05/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: 74155724abb3a0e02cc27dd8a8d144f142ee4b6f
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747723"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>Linux ワークロードのダウンロード、インストール、セットアップ

Windows で Visual Studio 2017 IDE を使用して、Linux 物理コンピューター、仮想マシン、または [Windows Subsystem for Linux](/windows/wsl/about) で実行する C++ プロジェクトを作成、編集、およびデバッグできます。 

Visual Studio プロジェクトに変換しなくても、CMake や他の任意のビルド システムを利用する既存のコード ベースで作業できます。 コード ベースがクロス プラットフォームの場合、Visual Studio 内から Windows と Linux の両方をターゲット設定できます。 たとえば、Visual Studio を使用して、Windows 上のコードを編集、デバッグ、プロファイルしてから、すぐに Linux のプロジェクトにターゲットを変更して、追加のテストを実行できます。 Linux ヘッダー ファイルが、ローカル コンピューターに自動的にコピーされ、そこで Visual Studio がそれらを使用して、IntelliSense の完全なサポート (ステートメント入力候補、定義へ移動など) を提供します。
 
これらのどのシナリオについても、**C++ による Linux 開発**ワークロードが必要です。 

## <a name="visual-studio-setup"></a>Visual Studio のセットアップ

1. Windows 検索ボックスに「Visual Studio インストーラー」と入力します。![Windows 検索ボックス](media/visual-studio-installer-search.png)
2. **アプリ**の結果でインストーラーを探し、それをダブルクリックします。 インストーラーが開いたら、**[変更]** を選択して **[ワークロード]** タブをクリックします。**[Other toolsets]\(その他のツールセット\)** まで下へスクロールして、**[C++ による Linux 開発]** ワークロードを選択します。

   ![Visual C++ for Linux Development ワークロード](media/linuxworkload.png)

1. CMake を使用するか、IoT または組み込みのプラットフォームを対象としている場合、**[C++ による Linux 開発]** の右側にある **[インストールの詳細]** ウィンドウに移動して、**[オプション コンポーネント]** を展開し、必要なコンポーネントを選択します。

    **Visual Studio 2017 バージョン 15.4 以降**<br/>:Visual Studio に Linux C++ ワークロードをインストールすると、Linux の CMake サポートが既定で選択されます。

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

## <a name="ensure-you-have-cmake-38-on-the-remote-linux-machine"></a>リモート Linux マシンに CMake 3.8 があることを確認する

Linux distro には古いバージョンの CMake が含まれている場合があります。 Visual Studio で CMake を利用するには、CMake 3.8 で導入されたサーバー モードに対応する必要があります。 Microsoft から提供されている CMake 変数の場合は、[https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) から最新のビルド済みバイナリを Linux マシンにダウンロードします。
