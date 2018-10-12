---
title: Visual Studio で C++ の Linux ワークロードをインストールする | Microsoft Docs
description: Visual Studio で C++ の Linux ワークロードをダウンロード、インストール、セットアップする方法について説明します。
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 403f1bcd8634c3f471f34ff1266501de5bf05d52
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601393"
---
# <a name="download-install-and-setup-the-linux-workload"></a>Linux ワークロードのダウンロード、インストール、セットアップ

Windows で Visual Studio IDE を使用して、Linux 物理コンピューター、仮想マシン、または [Windows Subsystem for Linux](/windows/wsl/about) で実行する C++ プロジェクトを作成、編集、およびデバッグできます。 これらのシナリオのいずれかについては、最初に **C++ による Linux 開発**ワークロードをインストールします。

## <a name="visual-studio-setup"></a>Visual Studio のセットアップ

1. Windows 検索メニューで「Visual Studio インストーラー」と入力して、**[アプリ]** 結果から検索し、これをダブルクリックします。 インストーラーが開いたら、**[変更]** を選択して **[ワークロード]** タブをクリックします。**[Other toolsets]\(その他のツールセット\)** まで下へスクロールして、**[C++ による Linux 開発]** ワークロードを選択します。

   ![Visual C++ for Linux Development ワークロード](media/linuxworkload.png)

1. CMake を使用するか、IoT または組み込みのプラットフォームを対象としている場合、**[C++ による Linux 開発]** の右側にある **[インストールの詳細]** ウィンドウに移動して、**[オプション コンポーネント]** を展開し、必要なコンポーネントを選択します。 

1. **[変更]** をクリックして、インストールを続行します。


## <a name="options-for-creating-a-linux-environment"></a>Linux 環境を作成するためのオプション

Linux マシンがまだない場合は、Azure で Linux 仮想マシンを作成できます。 詳細については、「[クイック スタート: Azure portal で Linux 仮想マシンを作成する](/azure/virtual-machines/linux/quick-create-portal)」を参照してください。

Windows 10 でのもう 1 つのオプションは、Windows Subsystem for Linux のアクティブ化です。 詳細については、「[Windows 10 Installation Guide](/windows/wsl/install-win10)」(Windows 10 インストール ガイド) を参照してください。

## <a name="linux-setup"></a>Linux のセットアップ

インストール先の Linux コンピューターには **openssh-server**、**g++**、**gdb**、**gdbserver** がインストールされていて、ssh デーモンが実行している必要があります。 Intellisense サポート対応のローカル コンピューターでリモート ヘッダーを自動同期するには、**zip** が必須です。 これらのアプリケーションがまだない場合は、次の手順でインストールできます。

1. Linux コンピューターのシェル プロンプトで次のコマンドを実行します。

   `sudo apt-get install openssh-server g++ gdb gdbserver zip`

   sudo コマンドにより、root パスワードの入力を求められる場合があります。  その場合は、入力して続行します。  完了すると、これらのサービスとツールがインストールされます。

1. 次のコマンドを実行し、Linux コンピューターで ssh サービスを実行します。

   `sudo service ssh start`

   サービスが開始されてバックグラウンドで実行し、接続を受け付けられる状態になります。
