---
title: C++ デスクトップ開発のための Visual Studio IDE の使用 | Microsoft Docs
ms.date: 06/08/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDE [C++]
- Visual Studio IDE [C++]
ms.assetid: d985c230-8e81-49d6-92be-2db9cac8d023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0678afc9d79499e4581feeca03b1a5bf9b7b963
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43131307"
---
# <a name="using-the-visual-studio-ide-for-c-desktop-development"></a>C++ デスクトップ開発のための Visual Studio IDE の使用

Visual Studio 統合開発環境 (IDE) は、大規模と小規模のコード プロジェクトの管理、コードの記述とリファクタリング、スタティック分析と高性能デバッグ ツールの両方を利用したエラーの検出と修正に役立つ一連の機能を備えています。 この一連の記事は、プロジェクトを管理し、コードを記述、テスト、デバッグして別のコンピューターに配置するために必要な手順を段階的に説明するように作られています。

## <a name="prerequisites"></a>必須コンポーネント

Visual Studio をまだインストールしていない場合、この機会にインストールしてください。 ダウンロードへのリンクおよびクイック チュートリアルは、「[Visual Studio での C++ サポートのインストール](../build/vscpp-step-0-installation.md)」を参照してください。 Visual Studio の一般的なインストール方法と不具合が生じた場合のトラブルシューティング方法の詳細については、「[Visual Studio のインストール](/visualstudio/install/install-visual-studio)」を参照してください。 **C++ によるデスクトップ開発**ワークロードを必ず選択し、既定ではインストールされない、C++ コンパイラー、ツールおよびライブラリを Visual Studio のインストール時に含めるようにします。

一連のチュートリアルは、Visual Studio、Visual C++ 言語、Windows デスクトップ開発に必要なコンポーネントをインストールしていることを前提としています。 C++ 言語の基礎について理解していることも前提としています。 C++ について学習する必要がある場合、さまざまな書籍や Web リソースをご利用いただけます。 Standard C++ Foundation Web サイトの [Get Started](https://isocpp.org/get-started) ページが入門としてお勧めです。

Visual Studio をまだインストールしていない場合、この機会にインストールしてください。 

**Visual Studio 2017 のインストール**

Visual Studio 2017 は [Visual Studio のダウンロード](http://www.visualstudio.com/downloads/download-visual-studio-vs.aspx)からダウンロードできます。 Visual Studio をインストールするときは、Visual C++ 開発ツールを必ず含めてください。既定ではインストールされません。 Visual Studio のインストール方法に関する詳細については、[Visual Studio のインストール](/visualstudio/install/install-visual-studio)に関するページを参照してください。

**Visual Studio 2015 のインストール**

 Visual Studio 2015 をインストールするには、[以前のバージョンの Visual Studio のダウンロード](https://www.visualstudio.com/vs/older-downloads/) ページに移動してください。 セットアップ プログラムを実行し、**カスタム インストール**で C++ コンポーネントを選択します。 

 一般に、Visual Studio 2015 のコンパイラを使用してコードをコンパイルする必要がある場合でも、Visual Studio 2017 を使用することを強くお勧めします。 詳細については、「[Visual Studio でネイティブ マルチ ターゲットを利用し、古いプロジェクトを作成する](../porting/use-native-multi-targeting.md)」を参照してください。

Visual Studio がインストールできたら、次へお進みください。

## <a name="get-started"></a>作業開始

Visual Studio IDE を利用して C++ アプリのビルドを始めるには、以下のトピックを順番に進めてください。 各トピックは、前のトピックで完了した作業を基盤とします。

- [チュートリアル: プロジェクトとソリューションの使用 (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)

- [チュートリアル: プロジェクトの構築 (C++)](../ide/walkthrough-building-a-project-cpp.md)

- [チュートリアル: プロジェクトのテスト (C++)](../ide/walkthrough-testing-a-project-cpp.md)

- [チュートリアル: プロジェクトのデバッグ (C++)](../ide/walkthrough-debugging-a-project-cpp.md)

- [チュートリアル: プログラムの配置 (C++)](../ide/walkthrough-deploying-your-program-cpp.md)

## <a name="next-steps"></a>次の手順

以上のチュートリアルを完了したら、独自のプロジェクトの構築を始められます。 Visual C++ 開発に関する情報とリソースが必要であれば、「[Visual Studio の Visual C++](../visual-cpp-in-visual-studio.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Visual Studio を使用した開発の開始](/visualstudio/ide/get-started-developing-with-visual-studio)