---
title: NMake プロパティ ページ (Windows C++)| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
dev_langs:
- C++
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29d10b35b0855e34826c10b813a2df48cd84cfef
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711972"
---
# <a name="nmake-property-page"></a>NMake プロパティ ページ
**[NMake]** プロパティ ページでは、NMake プロジェクトのビルド設定を指定できます。  
  
NMake プロジェクトの詳細については、「[Creating a Makefile Project](../ide/creating-a-makefile-project.md)」 (メイクファイル プロジェクトの作成) を参照してください。 Windows 以外のメイクファイル プロジェクトについては、「[メイクファイル プロジェクトのプロパティ (Linux C++)](../linux/prop-pages/makefile-linux.md)」、「[一般的なプロジェクト プロパティ (Android C++ メイクファイル)](/visualstudio/cross-platform/general-makefile-android-prop-page)」または「[NMake のプロパティ (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page)」を参照してください。
  
**[NMake]** プロパティ ページには、以下のプロパティがあります。  
  
## <a name="uielement-list"></a>UIElement の一覧  

- **ビルド コマンド ライン**

   **[ビルド]** が **[ビルド]** メニューでクリックされたときに実行されるコマンドを指定します。  
  
- **すべてリビルド コマンド ライン**

   **[すべてリビルド]** が **[ビルド]** メニューでクリックされたときに実行されるコマンドを指定します。  
  
- **クリーン コマンド ライン**

   **[クリーン]** が **[ビルド]** メニューでクリックされたときに実行されるコマンドを指定します。  
  
- **出力**

   コマンド ラインの出力が含まれるファイルの名前を指定します。 既定では、このファイル名はプロジェクト名に基づきます。  
  
- **プリプロセッサの定義**

   ソース ファイルを使用する任意のプリプロセッサの定義を指定します。 既定値は、現在のプラットフォームと構成によって決定されます。  
  
- **インクルードの検索パス**

   コンパイラでインクルード ファイルを検索するディレクトリを指定します。  
  
- **強制インクルード**

   プロジェクト ファイルに含まれない場合でも、プリプロセッサによって自動的に処理されるファイルを指定します。  
  
- **アセンブリの検索パス**

   .NET アセンブリを解決しようとするときに、.NET Framework で検索するディレクトリを指定します。  
  
- **アセンブリの強制使用**

   .NET Framework で自動的に処理されるアセンブリを指定します。  
  
- **その他のオプション**

   C++ ファイルを解析するときに使用する IntelliSense に対する追加のコンパイラ スイッチを指定します。  
  
**[NMake]** プロパティ ページにアクセスする方法については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」を参照してください。  
  
このプロジェクトのメンバーにプログラムを使ってアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)   
 [方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする](../ide/how-to-enable-intellisense-for-makefile-projects.md)