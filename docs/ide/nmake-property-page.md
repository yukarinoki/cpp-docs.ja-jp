---
title: '[NMake] プロパティ ページ (Windows C++) |Microsoft ドキュメント'
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
ms.openlocfilehash: f156d69467f00c4c4a62ec84d3b870e2999d7115
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-property-page"></a>NMake プロパティ ページ
**NMake**プロパティ ページ (nmake の) プロジェクトのビルド設定を指定できます。  
  
 (Nmake の) プロジェクトの詳細については、次を参照してください。[メイクファイル プロジェクトの作成](../ide/creating-a-makefile-project.md)です。 Non_Windows メイクファイル プロジェクトの場合、次を参照してください[メイクファイル プロジェクトのプロパティ (C++ の Linux)](../linux/prop-pages/makefile-linux.md)、[プロジェクト プロパティの [全般] (Android c のメイクファイル)](/visualstudio/cross-platform/general-makefile-android-prop-page)または[NMake プロパティ (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).
  
 **NMake**プロパティ ページには、次のプロパティが含まれています。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **コマンド ライン ビルドします。**  
 ときに実行するコマンドを指定**ビルド**でクリックされた、**ビルド**メニュー。  
  
 **すべてリビルド コマンドライン**  
 ときに実行するコマンドを指定**すべてリビルド**でクリックされた、**ビルド**メニュー。  
  
 **クリーン コマンドライン**  
 ときに実行するコマンドを指定**クリーン**でクリックされた、**ビルド**メニュー。  
  
 **出力**  
 コマンドラインの出力を格納するファイルの名前を指定します。 既定では、このファイル名は、プロジェクト名に基づきます。  
  
 **プリプロセッサの定義**  
 ソース ファイルで使用している任意のプリプロセッサの定義を指定します。 既定値は、現在のプラットフォームと構成によって決まります。  
  
 **インクルード検索パス**  
 コンパイラがインクルード ファイルを検索するディレクトリを指定します。  
  
 **強制的に含まれています**  
 プロジェクト ファイルでない含まれている場合でも、プリプロセッサが自動的に処理するファイルを指定します。  
  
 **アセンブリ検索パス**  
 .NET Framework が検索時にディレクトリを指定します、.NET アセンブリを解決するのには trys します。  
  
 **アセンブリの使用を強制**  
 .NET Framework を自動的に処理するアセンブリを指定します。  
  
 **その他のオプション**  
 IntelliSense の C++ ファイルを解析するときに使用するために、追加のコンパイラ スイッチを指定します。  
  
 アクセスする方法については、 **NMake**プロパティ ページを参照してください[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。  
  
 このオブジェクトのメンバーをプログラムでアクセスする方法については、次を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>です。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)   
 [方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする](../ide/how-to-enable-intellisense-for-makefile-projects.md)