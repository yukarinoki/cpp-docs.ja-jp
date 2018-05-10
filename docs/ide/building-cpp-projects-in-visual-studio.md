---
title: Visual Studio での C++ プロジェクトのビルド |Microsoft ドキュメント
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="building-c-projects-in-visual-studio"></a>Visual Studio での C++ プロジェクトのビルド
Visual Studio 統合開発環境 (IDE) では、ソリューション全体または 1 つのプロジェクトのみをビルドする複数の方法があります。 また、ビルド設定を変更し、カスタム ビルド ステップを指定して、開発プロセスを効率的にすることもできます。  
  
 Visual Studio で開いて、選択された状態では、ソリューションを構築する**ソリューション エクスプ ローラー**、することができます。  
  
-   メニュー バーの **[ビルド]**、 **[ソリューションのビルド]** の順にクリックします。  
  
-   または、**ソリューション エクスプ ローラー**ソリューションのショートカット メニューを開きを選択し、**ソリューションのビルド**です。  
  
-   または、F7 キーを押します。 (これは、C/C++ 開発設定の既定のキーボード ショートカットです)。  
  
-   または、[コマンド ウィンドウ](/visualstudio/ide/reference/command-window)(メニュー バーで、次のように選択します。**ビュー**、**その他のウィンドウ**、**コマンド ウィンドウ**)、入力`Build.BuildSolution`です。  
  
-   または、[サイド](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box)ボックスに、入力`build build solution`です。  
  
 選択されているプロジェクトをビルドする**ソリューション エクスプ ローラー**、することができます。  
  
-   メニュー バーで、次のように選択します。**ビルド**、**ビルド\<プロジェクト名 >** です。  
  
-   または、**ソリューション エクスプ ローラー**プロジェクトのショートカット メニューを開きを選択し、**ビルド**です。  
  
-   または、コマンド ウィンドウ (メニュー バーで、次のように選択します。**ビュー**、**その他のウィンドウ**、**コマンド ウィンドウ**)、入力`Build.BuildOnlyProject`です。  
  
-   または、クイック起動ボックスで、次のように入力します。`build project only build only <project name>`です。  
  
 Visual Studio で Visual C++ アプリケーションをビルドする場合、プロジェクトの [プロパティ ページ] ダイアログ ボックスでビルドの設定の多くを変更できます。 プロジェクトのプロパティを設定する方法については、次を参照してください。[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。  
  
 例については、IDE を使用して、作成、ビルド、および C++ プロジェクトをデバッグする方法について、次を参照してください。[チュートリアル: C++ での Visual Studio IDE の調査](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)です。 IDE を使用して、C + を構築する方法の例については +/CLR プロジェクトを参照してください[チュートリアル: Visual Studio で CLR を対象とする C++ プログラムのコンパイル](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)です。 例については、IDE を使用して、Windows ランタイム アプリを作成する方法について、次を参照してください。 [C++ を使った初めての Windows ランタイム アプリを作成する](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx)です。  
  
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
 [Vc++ ディレクトリの場合、プロジェクトでは、オプション ダイアログ ボックス](vcpp-directories-property-page.md)  
 (MSBuild プロジェクトの場合のみ)インクルード ファイル、ライブラリ ファイル、およびソース コード ファイル、ビルド時に、実行可能ファイルの検索パスを変更する方法について説明します。  
  
 [コードのコンパイルとビルド](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Visual Studio でのビルドについて説明します。  
  
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)  
 コマンド ラインまたは Visual Studio の統合開発環境からプログラムをビルドする方法について説明するトピックへのリンクがあります。  
  
 [C/C++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)  
 C++ でのプログラムのビルド、コンパイラ オプションとリンカー オプション、およびその他のビルド ツールの概要へのリンクがあります。  
  
 [旧バージョンの Visual C++ からのプロジェクトのアップグレード](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 新しいバージョンのコンパイラ ツールセットを C++ プロジェクトのアップグレードに関する問題を説明するトピックへのリンクを提供します。  
  
[Visual C++ 移植とアップグレードのガイド](../porting/visual-cpp-porting-and-upgrading-guide.md)  
  Visual Studio 以外のツールを使用して作成されたアプリケーションを移行する方法と、Visual Studio の以前のバージョンで作成された C++ アプリケーションをアップグレードする方法の詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [ユニバーサル Windows アプリ (C++)](../windows/universal-windows-apps-cpp.md)