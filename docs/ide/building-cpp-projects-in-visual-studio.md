---
title: Visual Studio での C++ プロジェクトのビルド | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, building
- projects [C++], building
- builds [C++], about building in Visual Studio
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7008e7fe670471301968482fbd4c6c758f0ff5e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340503"
---
# <a name="building-c-projects-in-visual-studio"></a>Visual Studio での C++ プロジェクトのビルド
Visual Studio 統合開発環境 (IDE) では、ソリューション全体または 1 つのプロジェクトのみをビルドする複数の方法があります。 また、ビルド設定を変更し、カスタム ビルド ステップを指定して、開発プロセスを効率的にすることもできます。  
  
 Visual Studio で開いており、**ソリューション エクスプローラー**で選択したソリューションをビルドするために、次の操作を行うことができます。  
  
-   メニュー バーの **[ビルド]**、 **[ソリューションのビルド]** の順にクリックします。  
  
-   または、**ソリューション エクスプローラー**でソリューションのショートカット メニューを開き、**[ソリューションのビルド]** を選択します。  
  
-   または、F7 キーを押します。 (これは、C/C++ 開発設定の既定のキーボード ショートカットです)。  
  
-   または、[コマンド ウィンドウ](/visualstudio/ide/reference/command-window) (メニュー バーで **[表示]**、**[その他のウィンドウ]**、**[コマンド ウィンドウ]** の順に選択) で、「`Build.BuildSolution`」と入力します。  
  
-   または、[[クイック起動]](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) ボックスに、「`build build solution`」と入力します。  
  
 **ソリューション エクスプローラー**で選択したプロジェクトをビルドするために、次の操作を行うことができます。  
  
-   メニュー バーで、**[ビルド]**、**[\<プロジェクト名> のビルド]** の順に選択します。  
  
-   または、**ソリューション エクスプローラー**でプロジェクトのショートカット メニューを開き、**[ビルド]** を選択します。  
  
-   または、コマンド ウィンドウ (メニュー バーで **[表示]**、**[その他のウィンドウ]**、**[コマンド ウィンドウ]** の順に選択) で、「`Build.BuildOnlyProject`」と入力します。  
  
-   または、[クイック起動] ボックスに、「`build project only build only <project name>`」と入力します。  
  
 Visual Studio で Visual C++ アプリケーションをビルドする場合、プロジェクトの [プロパティ ページ] ダイアログ ボックスでビルドの設定の多くを変更できます。 プロジェクトのプロパティの設定方法については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」を参照してください。  
  
 IDE を使用して C++ プロジェクトを作成、ビルド、およびデバッグする方法の例については、「[Walkthrough: Explore the Visual Studio IDE with C++](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)」(チュートリアル: C++ での Visual Studio IDE の調査) を参照してください。 IDE を使用して C++/CLR プロジェクトをビルドする方法の例については、「[チュートリアル: Visual Studio で CLR をターゲットにした C++ プログラムのコンパイル](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)」を参照してください。 IDE を使用して Windows ランタイム アプリを作成する方法の例については、「[Create your first Windows Runtime app using C++](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx)」(C++ を使った初めての Windows ランタイム アプリの作成) を参照してください。  
  
 ビルド、ビルド設定の変更、およびカスタム ビルド ステップの指定を行う方法の詳細については、次の記事を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)  
 統合開発環境でビルド プロセスをカスタマイズする方法について説明します。  
  
 [ビルドのコマンドとプロパティの共通マクロ](../ide/common-macros-for-build-commands-and-properties.md)  
 文字列を入力できる場所で使用できるマクロを一覧表示します。  
  
 [外部プロジェクトのビルド](../ide/building-external-projects.md)  
 統合開発環境外の機能を使用するプロジェクトのビルドについて説明します。  
  
 [プロジェクト ファイル](../ide/project-files.md)  
 .vcxproj ファイルの XML データ構造を示します。  
  
## <a name="related-sections"></a>関連項目  
 [VC++ ディレクトリ、プロジェクト、オプション ダイアログ ボックス](vcpp-directories-property-page.md)  
 (MSBuild プロジェクトの場合のみ) ビルド時の実行可能ファイル、インクルード ファイル、ライブラリ ファイル、およびソース コード ファイルの検索パスの変更方法について説明します。  
  
 [コードのコンパイルとビルド](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Visual Studio でのビルドについて説明します。  
  
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)  
 コマンド ラインまたは Visual Studio の統合開発環境からプログラムをビルドする方法について説明するトピックへのリンクがあります。  
  
 [C/C++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)  
 C++ でのプログラムのビルド、コンパイラ オプションとリンカー オプション、およびその他のビルド ツールの概要へのリンクがあります。  
  
 [旧バージョンの Visual C++ からのプロジェクトのアップグレード](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 より新しいバージョンのコンパイラ ツールセットへの C++ プロジェクトのアップグレードに関する問題を説明するトピックへのリンクを提供します。  
  
[Visual C++ 移植とアップグレードのガイド](../porting/visual-cpp-porting-and-upgrading-guide.md)  
  Visual Studio の旧バージョンで作成された C++ アプリケーションをアップグレードする方法と、Visual Studio 以外のツールを使用して作成されたアプリケーションを移行する方法について詳しく説明します。  
  
## <a name="see-also"></a>参照  
 [ユニバーサル Windows アプリ (C++)](../windows/universal-windows-apps-cpp.md)