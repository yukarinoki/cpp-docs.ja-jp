---
title: 'チュートリアル: プロジェクトとソリューションの使用 (C++) | Microsoft Docs'
ms.custom: ''
ms.date: 12/13/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f62b2317669949473c8b0e68ad4410a3d9b03806
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339136"
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>チュートリアル: プロジェクトとソリューションの使用 (C++)

ここでは、Visual Studio で C++ プロジェクトを作成し、コードを追加し、プロジェクトをビルドして実行する方法について説明します。 このチュートリアルのプロジェクトは、何人のプレーヤーが各種のカード ゲームを実行しているを追跡するプログラムです。

Visual Studio では、作業内容はプロジェクトとソリューションに整理されます。 ソリューションには、DLL とその DLL を参照する実行可能ファイルなど、複数のプロジェクトを含めることができます。 詳しくは、「[ソリューションおよびプロジェクト](/visualstudio/ide/solutions-and-projects-in-visual-studio)」をご覧ください。

## <a name="before-you-start"></a>開始する前に

このチュートリアルを完了するには、Visual Studio 2017 バージョン 15.3 以降が必要です。 コピーが必要な場合は、「[Install C++ support in Visual Studio](../build/vscpp-step-0-installation.md)」 (Visual Studio での C++ のインストール サポート) という簡潔なガイドがあります。 まだ行っていない場合は、"Hello, World" チュートリアルでインストールした後に、次の手順に従って、Visual C++ が正しくインストールされ、すべてが機能していることを確認します。

C++ 言語の基本を理解していて、コンパイラ、リンカー、およびデバッガーの用途を知っている場合に役立ちます。 また、チュートリアルでは、Windows とメニュー、ダイアログの使用方法に精通していることを前提としています。

## <a name="create-a-project"></a>プロジェクトを作成する

プロジェクトを作成するには、まずプロジェクトの種類のテンプレートを選択します。 プロジェクトのそれぞれの種類で、Visual Studio はコンパイラの設定と、その種類に応じて、後で変更できるスタート コードを生成します。

### <a name="to-create-a-project"></a>プロジェクトを作成するには

1. メニュー バーで **[ファイル] > [新規] > [プロジェクト]** の順にクリックします。

1. **[新しいプロジェクト]** ダイアログ ボックスの左ウィンドウで、**[インストール済み]** を展開し、**[Visual C++]** を選択します (まだ開いていない場合)。

1. 中央のペインのインストールされたテンプレートの一覧で、**[Windows コンソール アプリケーション]** を選択します。

1. **[名前]** ボックスにプロジェクトの名前を入力します。 この例では「**Game**」と入力します。

   **[場所]** ドロップダウン リストに表示される既定の場所をそのまま使用するか、別の場所を入力するか、または **[参照]** を選択してプロジェクトを保存するディレクトリを参照できます。

   プロジェクトを作成すると、Visual Studio により、そのプロジェクトがソリューションに配置されます。 既定では、ソリューション名はプロジェクト名と同じです。 **[ソリューション名]** ボックスの名前を変更できますが、この例では既定の名前を使用します。

1. **[OK]** ボタンを選択すると、プロジェクトが作成されます。

   Visual Studio により新しいソリューションとプロジェクト ファイルが作成され、生成された Game.cpp ソース コード ファイルのエディターが開かれます。

## <a name="organize-projects-and-files"></a>プロジェクトとファイルを整理する

**ソリューション エクスプローラー**を使用して、ソリューションのプロジェクト、ファイル、その他のリソースを整理および管理できます。

ここでは、クラスをプロジェクトに追加する方法を説明します。 クラスを追加すると、Visual Studio は、対応する .h ファイルと .cpp ファイルを追加します。 結果は**ソリューション エクスプローラー**で確認できます。

### <a name="to-add-a-class-to-a-project"></a>プロジェクトにクラスを追加するには

1. Visual Studio で**ソリューション エクスプローラー** ウィンドウが表示されない場合は、メニュー バーで **[表示] > [ソリューション エクスプローラー]** の順にクリックします。

1. **ソリューション エクスプローラー**で **Game** プロジェクトを選択します。 メニュー バーで **[プロジェクト] > [クラスの追加]** の順に選択します。

1. **[クラスの追加]** ダイアログで、**[クラス名]** ボックスに「*Cardgame*」と入力します。 既定のファイル名と設定を変更しないでください。 **[OK]** を選択します。

   Visual Studio により新しいファイルが作成され、プロジェクトに追加されます。 これらは**ソリューション エクスプローラー** ウィンドウで確認できます。 Cardgame.h と Cardgame.cpp ファイルがエディターで開かれます。

1. Cardgame.h ファイルを編集し、次の変更を行います。

   - クラス定義の左中かっこの後ろに、プライベート データ メンバーを 2 つ追加します。
      <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Visual Studio で生成される既定のコンストラクターを変更します。 `public:` アクセス指定子の後で、次のような行を探します。

      `Cardgame();`

      このコンストラクターを、"*players*" という名前の型 `int` の 1 個のパラメーターを受け取るように変更します。

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - 既定のデストラクターの後に、*GetParticipants* という名前の `static int` メンバー関数のインライン宣言を追加します。これは、パラメーターを受け取らず `totalParticipants` の値を返します。

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->
      `static int GetParticipants() { return totalParticipants; }`

   変更後、Cardgame.h ファイルは次のようになります。

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]-->
   ```cpp
   #pragma once
   class Cardgame
   {
       int players;
       static int totalParticipants;
   public:
       Cardgame(int players);
       ~Cardgame(void);
       static int GetParticipants() { return totalParticipants; }
   };
   ```

   行 `#pragma once` は、1 回だけヘッダー ファイルを含むようにコンパイラに指示します。 詳細については、「[once](../preprocessor/once.md)」を参照してください。 このヘッダー ファイルの他の C++ キーワードについては、「[class](../cpp/class-cpp.md)」、「[int](../cpp/fundamental-types-cpp.md)」、「[static](../cpp/storage-classes-cpp.md)」、および「[public](../cpp/public-cpp.md)」を参照してください。

1. 編集ウィンドウの上部で **[Cardgame.cpp]** タブをクリックして編集のために開きます。

1. ファイル内のすべてを削除して、このコードと置き換えます。

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]-->
   ```cpp
   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   int Cardgame::totalParticipants = 0;

   Cardgame::Cardgame(int players)
       : players(players)
   {
       totalParticipants += players;
       cout << players << " players have started a new game.  There are now "
            << totalParticipants << " players in total." << endl;
   }

   Cardgame::~Cardgame()
   {
   }
   ```

   > [!NOTE]
   > コードを入力するときにオート コンプリートを使用できます。 たとえば、キーボードでこのコードを入力する場合、「*pl*」または「*tot*」を入力してから、Ctrl キーを押しながら Space キーを押すことができます。 オート コンプリートにより `players` または `totalParticipants` が入力されます。

## <a name="add-test-code-to-your-main-function"></a>main 関数にテスト コードを追加する

新しい関数をテストするアプリにいくつかのコードを追加します。

### <a name="to-add-test-code-to-the-project"></a>プロジェクトにテスト コードを追加するには

1. Game.cpp エディター ウィンドウで、既存のコードを次のコードに置き換えます。

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]-->
   ```cpp
   // Game.cpp : Defines the entry point for the console application.
   //

   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   void PlayGames()
   {
       Cardgame bridge(4);
       Cardgame blackjack(8);
       Cardgame solitaire(1);
       Cardgame poker(5);
   }

   int main()
   {
       PlayGames();
       return 0;
   }
   ```
このコードは、テスト関数 `PlayGames` をソース コードに追加し、それを `main` で呼び出します。 

## <a name="build-and-run-your-app-project"></a>アプリ プロジェクトをビルドして実行する

次に、プロジェクトをビルドし、アプリを実行します。

### <a name="to-build-and-run-the-project"></a>プロジェクトをビルドして実行するには

1. メニュー バーで、**[ビルド]、[ソリューションのビルド]** の順にクリックします。

   ビルドからの出力は、**[出力]** ウィンドウに表示されます。 ビルドが成功した場合、出力は次のようになります。

   ```Output
   1>------ Build started: Project: Game, Configuration: Debug Win32 ------
   1>  stdafx.cpp
   1>  Game.cpp
   1>  Cardgame.cpp
   1>  Generating Code...
   1>  Game.vcxproj -> C:\Users\username\Source\Repos\Game\Debug\Game.exe
   ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
   ```

   **[出力]** ウィンドウはビルド構成によって異なる手順を表示しますが、プロジェクトのビルドが成功した場合、最後の行は次のような出力になります。

   ビルドが成功しなかった場合は、コードを、前の手順で示されたコードと比較してください。

1. プロジェクトを実行するには、メニュー バーで **[デバッグ] > [デバッグなしで開始]** の順にクリックします。 コンソール ウィンドウが表示され、出力はこのようになります。

   ```Output
   4 players have started a new game.  There are now 4 players in total.
   8 players have started a new game.  There are now 12 players in total.
   1 players have started a new game.  There are now 13 players in total.
   5 players have started a new game.  There are now 18 players in total.
   ```
コンソール ウィンドウを閉じるにはキーを押します。

これでアプリ プロジェクトとソリューションが正常にビルドされました。 Visual Studio で C++ コード プロジェクトをビルドする方法についてさらに学習するには、チュートリアルを続行します。

## <a name="next-steps"></a>次の手順

**前:** [C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)  
**次:** [チュートリアル: プロジェクトの構築 (C++)](../ide/walkthrough-building-a-project-cpp.md)

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)  
[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)