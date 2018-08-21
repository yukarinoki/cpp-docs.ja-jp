---
title: Visual Studio で C++ の Linux ワークロードをインストールする | Microsoft Docs
description: Visual Studio で C++ の Linux ワークロードをダウンロード、インストール、セットアップする方法について説明します。
ms.custom: ''
ms.date: 07/20/2018
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
ms.openlocfilehash: e33b9ac72ca7691ccbb80a9a30349d3a1e31e194
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207560"
---
# <a name="download-install-and-setup-the-linux-workload"></a>Linux ワークロードのダウンロード、インストール、セットアップ

Visual Studio IDE を使用して Linux 上で C++ プロジェクトを作成およびデバッグするには、**C++ による Linux 開発**のワークロードをインストールする必要があります。

## <a name="visual-studio-setup"></a>Visual Studio のセットアップ
1. Visual Studio インストーラーを起動し、**[C++ による Linux 開発]** ワークロードを選びます。

   ![Visual C++ for Linux Development 拡張機能](media/linuxworkload.png)

2. **[インストール]** をクリックしてインストールを続けます。

## <a name="linux-setup"></a>Linux のセットアップ
インストール先の Linux コンピューターには **openssh-server**、**g++**、**gdb**、**gdbserver** がインストールされていて、ssh デーモンが実行している必要があります。  これらがまだない場合は、次のようにしてインストールできます。
 
1. Linux コンピューターのシェル プロンプトで次のコマンドを実行します。

   `sudo apt-get install openssh-server g++ gdb gdbserver`

   sudo コマンドにより、root パスワードの入力を求められる場合があります。  その場合は、入力して続行します。  完了すると、これらのサービスとツールがインストールされます。

1. 次のコマンドを実行し、Linux コンピューターで ssh サービスを実行します。

   `sudo service ssh start`
   
   サービスが開始されてバックグラウンドで実行し、接続を受け付けられる状態になります。
