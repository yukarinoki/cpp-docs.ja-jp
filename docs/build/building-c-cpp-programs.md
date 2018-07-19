---
title: C/C++ プログラムのビルド |Microsoft ドキュメント
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
ms.openlocfilehash: 2894c503dde89668bfb90b615c7b0966fe5fe2e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360976"
---
# <a name="building-cc-programs"></a>C/C++ プログラムのビルド

Visual C++ プロジェクトは、Visual Studio またはコマンド ラインでビルドできます。 Visual Studio IDE を使用して[MSBuild](../build/msbuild-visual-cpp.md)プロジェクトおよびソリューションをビルドします。 コマンド ラインでは、C/C++ コンパイラ (cl.exe) と リンカー (link.exe) を使用して単純なプロジェクトをビルドできます。 コマンドラインでより複雑なプロジェクトを作成するには、MSBuild を使用することができますか[NMAKE](../build/nmake-reference.md)です。 使用する方法の概要についての[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]プロジェクトおよびソリューションをビルドするを参照してください。[コンパイルとビルド](/visualstudio/ide/compiling-and-building-in-visual-studio)です。  
  
## <a name="in-this-section"></a>このセクションの内容  

[Visual Studio での C++ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)  
Visual Studio IDE を使用して C/C++ プロジェクトをビルドする方法について説明します。  
  
[コマンドラインでの C/C++ コードのビルド](../build/building-on-the-command-line.md)  
Visual Studio に含まれている C/C++ コマンド ライン コンパイラおよびビルド ツールの使用方法について説明します。  
  
[C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
アプリケーションの分離、side-by-side アセンブリなどの考え方に基づいた Windows デスクトップ アプリケーションの配置モデルについて説明します。  
  
[C/C++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)  
C++ でのプログラムのビルド、コンパイラ オプションとリンカー オプション、およびさまざまなビルド ツールに関する参照記事へのリンクがあります。  
  
[64 ビット、x64 ターゲット用の Visual C の構成](../build/configuring-programs-for-64-bit-visual-cpp.md)  
64 ビット ツール セットを使用し、64 ビット アーキテクチャをターゲットとして Visual Studio とコマンド ラインを設定する方法について説明し、コードを 64 ビット アーキテクチャに移行するときに一般的に発生する、移行に関する問題について説明します。  
  
[ARM プロセッサ用の Visual C ++ の構成する](../build/configuring-programs-for-arm-processors-visual-cpp.md)  
ARM プロセッサで使用される用語について説明し、コードを ARM アーキテクチャに移行するときに一般的に発生する、移行に関する問題について説明します。  
  
[Windows XP 用プログラムの構成](../build/configuring-programs-for-windows-xp.md)  
Windows XP 開発をターゲットとしてプラットフォーム ツールセットを設定する方法について説明します。  
  
## <a name="related-sections"></a>関連項目  
 [コードのコンパイルとビルド](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Visual Studio のビルド システムとツールについて説明します。