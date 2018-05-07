---
title: 'チュートリアル: プロジェクトとソリューション (C++) の操作 |Microsoft ドキュメント'
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>チュートリアル: プロジェクトとソリューションの使用 (C++)

ここでは、Visual Studio で C++ プロジェクトを作成し、コードを追加し、プロジェクトをビルドして実行する方法について説明します。 このチュートリアルのプロジェクトは、何人のプレーヤーが各種のカード ゲームを実行しているを追跡するプログラムです。

Visual Studio で、プロジェクトとソリューションの作業が編成されます。 ソリューションには、DLL とその DLL を参照する実行可能ファイルなど、複数のプロジェクトを含めることができます。 詳しくは、「[ソリューションおよびプロジェクト](/visualstudio/ide/solutions-and-projects-in-visual-studio)」をご覧ください。

## <a name="before-you-start"></a>開始する前に

このチュートリアルを完了するには、必要が Visual Studio 2017 バージョン 15.3 またはそれ以降。 短いガイドは、コピーを必要がある場合: [Visual Studio での C++ のインストール サポート](../build/vscpp-step-0-installation.md)です。 実行まだしていない場合は場合、次の手順に従います Visual C が正しくインストールされているかどうかを確認する「こんにちは, World」のチュートリアルと、インストール後にすべてが機能します。

C++ 言語の基本を理解して、コンパイラ、リンカー、およびデバッガー用途を知っている場合に役立ちます。 また、チュートリアルでは Windows とメニュー、ダイアログ ボックスを使用する方法に精通している想定しています

## <a name="create-a-project"></a>プロジェクトを作成する

プロジェクトを作成するには、まずプロジェクトの種類のテンプレートを選択します。 各プロジェクトの種類の Visual Studio コンパイラの設定と -種類に応じて-後で変更できるスタート コードを生成します。

### <a name="to-create-a-project"></a>プロジェクトを作成するには

1. メニュー バーで、次のように選択します。**ファイル > 新規 > プロジェクト**です。

1. 左側のウィンドウで、**新しいプロジェクト** ダイアログ ボックスで、展開**インストール済み**選択**Visual C**まだ開いていない場合は、します。

1. 中央のウィンドウでインストールされたテンプレートの一覧で選択**Windows コンソール アプリケーション**です。

1. プロジェクトの名前を入力、**名前**ボックス。 この例では、入力**ゲーム**です。

   既定の場所を受け入れることができます、**場所**ドロップダウン リストを別の場所を入力または選択、**参照**プロジェクトを保存するディレクトリに移動するボタンをクリックします。

   プロジェクトを作成するときに Visual Studio は、ソリューションでプロジェクトを格納します。 既定では、ソリューション名はプロジェクト名と同じです。 内の名前を変更することができます、**ソリューション名**ボックスが、この例では、既定の名前を保持します。

1. **[OK]** ボタンを選択すると、プロジェクトが作成されます。

   Visual Studio では、新しいソリューションとプロジェクト ファイルを作成し、生成された Game.cpp ソース コード ファイルのエディターを開きます。

## <a name="organize-projects-and-files"></a>プロジェクトとファイルを整理します。

使用することができます**ソリューション エクスプ ローラー**を整理およびプロジェクト、ファイル、およびソリューションの他のリソースを管理します。

ここでは、クラスをプロジェクトに追加する方法を説明します。 クラスを追加すると、Visual Studio は、対応する .h および .cpp ファイルを追加します。 結果を確認できる**ソリューション エクスプ ローラー**です。

### <a name="to-add-a-class-to-a-project"></a>プロジェクトにクラスを追加するには

1. 場合、**ソリューション エクスプ ローラー**メニュー バーで、Visual Studio で、ウィンドウが表示されない場合、選択**ビュー > ソリューション エクスプ ローラー**です。

1. **ソリューション エクスプ ローラー**、select、**ゲーム**プロジェクト。 メニュー バーで、次のように選択します。**プロジェクト > クラスの追加**です。

1. **クラスの追加**ダイアログ ボックスで、入力*Cardgame*で、**クラス名**ボックス。 既定のファイル名と設定を変更しないでください。 **[OK]** を選択します。

   Visual Studio では、新しいファイルが作成され、プロジェクトに追加されます。 ご覧、**ソリューション エクスプ ローラー**ウィンドウです。 Cardgame.h と Cardgame.cpp ファイルはエディターで開かれます。

1. Cardgame.h ファイルを編集し、これらの変更を行います。

   - クラス定義の左中かっこの後ろに、プライベート データ メンバーを 2 つ追加します。
      <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Visual Studio で生成される既定のコンストラクターを変更します。 `public:` アクセス指定子の後で、次のような行を探します。

      `Cardgame();`

      この型の 1 つのパラメーターを受け取るコンス トラクターを変更`int`、名前付き*プレーヤー*です。

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - 既定のデストラクターの後のインライン宣言を追加、`static int`という名前のメンバー関数*GetParticipants*をパラメーターを受け取らないを返します、`totalParticipants`値。

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

   行`#pragma once`ヘッダー ファイルに 1 回だけを含めるようにコンパイラに指示します。 詳細については、次を参照してください。[したら](../preprocessor/once.md)です。 このヘッダー ファイルには、その他の C++ キーワードについては、次を参照してください。[クラス](../cpp/class-cpp.md)、 [int](../cpp/fundamental-types-cpp.md)、[静的](../cpp/storage-classes-cpp.md)、および[パブリック](../cpp/public-cpp.md)です。

1. 選択、 **Cardgame.cpp**ファイルを開いて編集する編集ペインの上部にあるタブ。

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
   > コードを入力するときにオート コンプリートを使用できます。 などの場合は、キーボードでは、このコードを入力すると、入力できます*pl*または *>.30*し ctrl キーを押しながら space キーを押します。 オート コンプリート入力`players`または`totalParticipants`します。

## <a name="add-test-code-to-your-main-function"></a>テストのコードを main 関数に追加します。

新しい関数をテストするアプリをいくつかのコードを追加します。

### <a name="to-add-test-code-to-the-project"></a>テスト コードをプロジェクトに追加するには

1. Game.cpp エディター ウィンドウでは、この既存のコードを置き換えます。

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
このコードで追加テスト関数の場合、 `PlayGames`、ソース コードと呼び出しで`main`です。 

## <a name="build-and-run-your-app-project"></a>ビルドおよび実行する、アプリ プロジェクト

次に、プロジェクトをビルドし、アプリを実行します。

### <a name="to-build-and-run-the-project"></a>プロジェクトをビルドして実行するには

1. メニュー バーで、**[ビルド]、[ソリューションのビルド]** の順にクリックします。

   ビルドからの出力に表示されます、**出力**ウィンドウです。 ビルドが成功した場合、出力は次のようになります。

   ```Output
   1>------ Build started: Project: Game, Configuration: Debug Win32 ------
   1>  stdafx.cpp
   1>  Game.cpp
   1>  Cardgame.cpp
   1>  Generating Code...
   1>  Game.vcxproj -> C:\Users\username\Source\Repos\Game\Debug\Game.exe
   ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
   ```

   **出力**ウィンドウで、ビルド構成によって異なる手順を表示できますが、プロジェクトのビルドが成功すると、最後の行のような出力ようになります。

   ビルドが成功しなかった場合、コードを前の手順で示すコードを比較します。

1. メニュー バーで、プロジェクトを実行するには選択**デバッグ > デバッグなしで開始**です。 コンソール ウィンドウが表示されますと、この出力のようになります。

   ```Output
   4 players have started a new game.  There are now 4 players in total.
   8 players have started a new game.  There are now 12 players in total.
   1 players have started a new game.  There are now 13 players in total.
   5 players have started a new game.  There are now 18 players in total.
   ```
コンソール ウィンドウを消去するキーを押します。

これでアプリのプロジェクトとソリューションを正常にビルドしたです。 Visual Studio での C++ コード プロジェクトをビルドする方法の詳細については、チュートリアルを続行します。

## <a name="next-steps"></a>次の手順

**前:** [C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)です。  
**次へ:** [チュートリアル: プロジェクトの構築 (C++)](../ide/walkthrough-building-a-project-cpp.md)です。

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)  
[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)