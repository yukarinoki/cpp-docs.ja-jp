---
title: C/C++ プログラムのビルド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- vcbuilding
- buildingaprogramVC
dev_langs:
- C++
helpviewer_keywords:
- builds [C++]
- Visual C++ projects, building
- projects [C++], building
- builds [C++], options
- Visual C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2792b49d7d3d3f107e39931ff62e6c4137c9c5ca
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723269"
---
# <a name="building-cc-programs"></a>C/C++ プログラムのビルド

Visual C++ プロジェクトは、Visual Studio またはコマンド ラインでビルドできます。 Visual Studio IDE を使用して[MSBuild](../build/msbuild-visual-cpp.md)プロジェクトおよびソリューションを構築します。 コマンド ラインでは、C/C++ コンパイラ (cl.exe) と リンカー (link.exe) を使用して単純なプロジェクトをビルドできます。 コマンドラインより複雑なプロジェクトを作成するには、MSBuild を使用することができますか[NMAKE](../build/nmake-reference.md)します。 Visual Studio を使用して、プロジェクトおよびソリューションを構築する方法の概要については、次を参照してください。[のコンパイルとビルド](/visualstudio/ide/compiling-and-building-in-visual-studio)します。

## <a name="in-this-section"></a>このセクションの内容

[Visual Studio で C++ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)Visual Studio IDE を使用して C/C++ プロジェクトをビルドする方法について説明します。

[コマンドラインで C/C++ コードをビルド](../build/building-on-the-command-line.md)C/C++ コマンド ライン コンパイラを使用し、Visual Studio に含まれているツールを構築する方法について説明します。

[C/C++ 分離アプリケーションとサイド バイ サイド アセンブリをビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)分離アプリケーションとサイド バイ サイド アセンブリの概念に基づく、Windows デスクトップ アプリケーションのデプロイ モデルについて説明します。

[C/C++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)プログラムの C++、コンパイラおよびリンカー オプション、ビルドに関する参照記事へのリンクを提供し、さまざまなツールをビルドします。

[Visual C の 64 ビット x64 構成ターゲット](../build/configuring-programs-for-64-bit-visual-cpp.md)Visual Studio とコマンドラインの両方が 64 ビット ツールセットを使用して構成する方法と 64 ビットのアーキテクチャをターゲットにする方法について説明し、コードが 64 ビットへ移動したときに、移行の一般的な問題をについて説明しますアーキテクチャ。

[ARM プロセッサ用の Visual C の構成](../build/configuring-programs-for-arm-processors-visual-cpp.md)、ARM プロセッサで使用される規則について説明し、コードが ARM アーキテクチャに移動したときに、移行の一般的な問題をについて説明します。

[Windows XP 用プログラムを構成する](../build/configuring-programs-for-windows-xp.md)プラットフォーム ツールセットをターゲットの Windows XP の開発に設定する方法について説明します。

## <a name="related-sections"></a>関連項目

[コンパイルとビルド](/visualstudio/ide/compiling-and-building-in-visual-studio)方法について説明します、Visual Studio は、システムおよびツールをビルドします。