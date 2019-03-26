---
title: サポートされるプラットフォーム (Visual C++)
ms.date: 11/04/2016
ms.technology: cpp-tools
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 373ac11ac26ddc1f9dbf1e1e16ae25dcf0e47f9f
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328702"
---
# <a name="supported-platforms-visual-c"></a>サポートされるプラットフォーム (Visual C++)

Visual Studio を使用してビルドしたアプリケーションは、次のようにさまざまなプラットフォームを対象にすることができます。

|オペレーティング システム|x86|X64|ARM|
|----------------------|---------|---------|---------|
|Windows XP|X\*|X\*||
|Windows Server 2003|X\*|X\*||
|Windows Vista|x|x||
|Windows Server 2008|x|x||
|Windows 7|x|x||
|Windows Server 2012 R2|x|x||
|Windows 8|x|x|x|
|Windows 8.1|x|x|x|
|Windows 10|x|x|x|
|Android \*\*|x|x|x|
|iOS \*\*|x|x|x|
|Linux \*\*\*|x|x|x|

\* Visual Studio 2017、Visual Studio 2015、Visual Studio 2013、Visual Studio 2012 Update 1 以降に含まれている Windows XP プラットフォーム ツールセットを使用して、Windows XP および Windows Server 2003 プロジェクトを構築できます。 このプラットフォーム ツールセットを使用する方法については、「[Windows XP 用プログラムの構成](build/configuring-programs-for-windows-xp.md)」を参照してください。 プラットフォーム ツールセットの変更に関する詳細は、「[方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更する](build/how-to-modify-the-target-framework-and-platform-toolset.md)」を参照してください。

\*\* Visual Studio 2017 インストーラーの **C++ によるモバイル開発**ワークロード (あるいは、Visual Studio 2015 セットアップのオプションの **Visual C++ for Cross Platform Mobile Development** コンポーネント) をインストールし、iOS または Android プラットフォームをターゲットにすることができます。 手順については、「[クロス プラットフォーム モバイル開発用の Visual C++ のインストール](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development)」を参照してください。 iOS コードをビルドするには、Mac コンピューターがあり、他の要件を満たしている必要があります。 前提条件とインストール手順については、「[iOS を使用してビルドするためのツールのインストールおよび構成](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios)」を参照してください。 ターゲット ハードウェアに合わせて、x86 または ARM コードをビルドできます。 iOS シミュレーター、Microsoft Visual Studio Emulator for Android、一部の Android デバイスのビルドには x86 構成を使用します。 iOS デバイスとほとんどのデバイスのビルドには ARM 構成を使用します。

\*\*\* Visual Studio 2017 インストーラーの **C++ による Linux 開発**ワークロードをインストールし、Linux プラットフォームをターゲットにすることができます。 方法については、「[Linux ワークロードのダウンロード、インストール、セットアップ](linux/download-install-and-setup-the-linux-development-workload.md)」を参照してください。 このツールセットは、サポートされているあらゆるアーキテクチャでビルドできるように、ターゲット マシンで実行可能ファイルをコンパイルします。

対象プラットフォームの構成を設定する方法については、「[How to: Configure Visual C++ Projects to Target 64-Bit, x64 Platforms](build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)」(方法: Visual C++ プロジェクトを 64 ビット、x64 プラットフォーム用に設定する) を参照してください。

## <a name="see-also"></a>関連項目

- [さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)
- [はじめに](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)
