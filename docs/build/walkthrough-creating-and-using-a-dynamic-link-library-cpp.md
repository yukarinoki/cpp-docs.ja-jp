---
title: 'チュートリアル: を作成し、独自のダイナミック リンク ライブラリ (C++) を使用して |Microsoft ドキュメント'
ms.custom: conceptual
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19c9c013d591f4c6de14ecd4a2c582d8f0f3e4d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392589"
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>チュートリアル: は、作成して、独自のダイナミック リンク ライブラリ (C++)

このステップ バイ ステップ チュートリアルでは、Visual Studio IDE を使用して、C++ で記述された独自ダイナミック リンク ライブラリ (DLL) を作成し、し、別の C++ アプリから使用する方法を示します。 Dll は、最も役に立つさまざまな Windows コンポーネントのいずれか。 アプリのサイズを縮小し、サービスし、アプリの拡張を容易にできるように、コードと、リソースを共有する方法としてそれらを使用できます。 このチュートリアルでは、いくつかの数学関数を実装する DLL を作成し、DLL から関数を使用するコンソール アプリを作成します。 その過程では、いくつかのプログラミング手法と Windows Dll での表記規則の概要を取得します。

このチュートリアルでは、次の作業について説明します。

- Visual Studio では、DLL プロジェクトを作成します。

- DLL にエクスポートされた関数および変数を追加します。

- Visual Studio でコンソール アプリ プロジェクトを作成します。

- 関数とコンソール アプリ内の DLL からインポートされた変数を使用します。

- 完成したアプリを実行します。

などの静的にリンクされるライブラリ DLL_エクスポート_変数、関数、およびリソース名、およびアプリ_インポート_それらの変数、関数、およびリソースを使用する名前。 スタティック ライブラリとは異なりは、Windows は、読み込み時に、またはリンク時に接続することではなく、実行時に DLL のエクスポートに、アプリ内のインポートを接続します。 Windows では、これらの接続を確立する、標準 C++ コンパイル モデルの一部でない余分な情報が必要です。 Visual C コンパイラでは、この追加情報を提供する c++ の一部の Microsoft 固有拡張機能を実装します。 移動するとこれらの拡張機能を説明します。

このチュートリアルは、次の 2 つの Visual Studio ソリューションを作成します。DLL をビルドしてするクライアント アプリをビルドします。 プラットフォーム呼び出しとリンク規則に一致する限り、その他の言語を使用してビルドされたアプリから呼び出すことができます、DLL は C 呼び出し規約を使用します。 クライアント アプリの使用_暗黙的リンク_Windows が読み込み時に DLL へのアプリをリンクします。 これにより、関数を呼び出して、DLL が指定した関数と同じように静的にリンクされたライブラリで、アプリができます。

このチュートリアルでは、いくつかの一般的な状況を扱われていません。 他のプログラミング言語での C++ Dll の使用は反映されません。 リソース専用 DLL を作成する方法が表示されません。 負荷時ではなく、実行時に Dll をロードする明示的なリンクの使用も表示されません。 安心 Visual C を使用して、これらすべての作業を行います。 Dll に関する詳細情報へのリンクを参照してください。 [Visual c の Dll](../build/dlls-in-visual-cpp.md)です。 暗黙的なリンクと明示的なリンクの詳細については、次を参照してください。[リンク方式の使い分けを使用する](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)です。 C 言語のリンケージ規則を使用する言語をプログラミングで使用するための C++ Dll の作成については、次を参照してください。 [C 言語の実行可能ファイルで使用するための C++ 関数のエクスポート](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)です。 .NET 言語で使用する Dll を作成する方法については、次を参照してください。 [Visual Basic アプリケーションから DLL 関数の呼び出し](../build/calling-dll-functions-from-visual-basic-applications.md)です。

このチュートリアルは Visual Studio 2017 を使用しますが、コードと説明の大半は以前のバージョンに適用されます。 Visual Studio 2017 バージョン 15.3 以降、新しいプロジェクトを作成する手順が変更されました。 このチュートリアルでは、新しいと古いバージョンの両方のプロジェクトを作成する方法について説明します。 Visual Studio のバージョンに対応するステップを参照してください。

## <a name="prerequisites"></a>必須コンポーネント

- Microsoft Windows 7 またはそれ以降のバージョンを実行するコンピューター。 Windows 10 は、最適な開発エクスペリエンスをお勧めします。

- Visual Studio 2017 のコピー。 ダウンロードして Visual Studio をインストールする方法については、次を参照してください。 [Visual Studio のインストール 2017](/visualstudio/install/install-visual-studio)です。 インストーラーを実行するときに、以下のことを確認、 **C++ を使用したデスクトップ開発**ワークロードがオンになっています。 Visual Studio をインストールしたときにこのワークロードをインストールしなかった場合、心配しないでください。 インストーラーをもう一度実行して、今すぐインストールします。

   ![C++ を使用したデスクトップ開発](media/desktop-development-with-cpp.png "C++ を使用したデスクトップの開発")

- Visual Studio IDE の基本的な使い方を理解します。 前に、の Windows デスクトップ アプリを使用している場合保持できます可能性があります。 概要については、次を参照してください。 [Visual Studio IDE 機能のツアー](/visualstudio/ide/visual-studio-ide)です。

- 進めるために、C++ 言語の基本の十分な理解します。 心配しないで、あまり複雑な何もしません。

## <a name="create-the-dll-project"></a>DLL プロジェクトを作成します。

この一連のタスクのには、コードを追加、およびビルドする DLL のプロジェクトを作成します。 を開始するには、Visual Studio IDE を起動し、する必要がある場合にサインインします。 Visual Studio 2017 15.3 のバージョンについては、先にします。 以前のバージョンについては、後で、のでスキップしたい場合。

### <a name="to-create-a-dll-project-in-visual-studio-2017-version-153-or-later"></a>15.3 またはそれ以降、Visual Studio 2017 バージョンの DLL プロジェクトを作成するには

1. メニュー バーで、次のように選択します。**ファイル**、**新規**、**プロジェクト**を開くには、**新しいプロジェクト** ダイアログ ボックス。

1. 左側のウィンドウで、**新しいプロジェクト** ダイアログ ボックスで、展開**インストール**と**Visual C**を選択し、必要に応じて**Windows デスクトップ**です。 中央のウィンドウで次のように選択します。 **Windows デスクトップ ウィザード**です。 入力`MathLibrary`で、**名**ボックスをプロジェクトの名前を指定します。

   ![MathLibrary プロジェクト](media/mathlibrary-new-project-name-153.png "MathLibrary プロジェクトの名前")

1. 選択、 **OK**を消去するボタン、**新しいプロジェクト**ダイアログと開始、 **Windows デスクトップ プロジェクト**ウィザード。

1. **Windows デスクトップ プロジェクト**ウィザードの **アプリケーションの種類****ダイナミック リンク ライブラリ (.dll)** です。

   ![Windows デスクトップ プロジェクト ウィザードで DLL を作成](media/mathlibrary-desktop-project-wizard-dll.png "Windows デスクトップ プロジェクト ウィザードで DLL を作成します。")

1. **[OK]** ボタンを選択すると、プロジェクトが作成されます。

> [!NOTE]
> Visual Studio 2017 15.3 のバージョンで、問題を解決するには、追加手順が必要です。 次の手順を実行するかどうかは、この変更を行う必要があります。 を参照してください。
>
>1. **ソリューション エクスプ ローラー**になっていない、選択した場合、 **MathLibrary**プロジェクトの下にある**ソリューション 'MathLibrary'** です。
>
>1. メニュー バーで、**[プロジェクト]**、**[プロパティ]** の順に選びます。
>
>1. 左側のウィンドウで、**プロパティ ページ**ダイアログ ボックスで、**プリプロセッサ****構成プロパティ**、 **C/C++** です。 内容を確認、**プリプロセッサの定義**プロパティです。<br/><br/>![プリプロセッサの定義のプロパティを調べて](media/mathlibrary-153bug-preprocessor-definitions-check.png "プロパティを確認するプリプロセッサの定義")<br/><br/>表示される場合**MATHLIBRARY&#95;エクスポート**で、**プリプロセッサの定義**何も変更する必要はありませんし、一覧表示します。 表示される場合**MathLibrary&#95;エクスポート**代わりに、し、次の手順に進みます。
>
>1. 上部にある、**プロパティ ページ**ダイアログ ボックスで、変更、**構成**ドロップダウンを**すべて構成**です。
>
>1. プロパティ ペインで選択用のエディット ボックスの横にあるドロップダウン コントロール**プリプロセッサの定義**を選択し**編集**です。<br/><br/>![プリプロセッサの定義のプロパティを編集](media/mathlibrary-153bug-preprocessor-definitions-property.png "プリプロセッサの定義のプロパティの編集")
>
>1. 上部ペインで、**プリプロセッサの定義**ダイアログ ボックスで、新しいシンボルを追加`MATHLIBRARY_EXPORTS`です。<br/><br/>![MATHLIBRARY_EXPORTS シンボル追加](media/mathlibrary-153bug-preprocessor-definitions-dialog.png "MATHLIBRARY_EXPORTS 記号を追加します。")
>
>1. 選択 **[ok]** を消去する、**プリプロセッサの定義**ダイアログ ボックスを選択し**OK**プロジェクト プロパティに変更を保存します。

### <a name="to-create-a-dll-project-in-older-versions-of-visual-studio"></a>Visual Studio の旧バージョンでは、DLL プロジェクトを作成するには

1. メニュー バーで、 **[ファイル]**、 **[新規作成]**、 **[プロジェクト]** の順にクリックします。

1. 左側のウィンドウで、**新しいプロジェクト**] ダイアログ ボックスで、展開**インストール**、**テンプレート**を選択し、 **Visual C**中央の [ペインで、 **Win32 コンソール アプリケーション**です。 入力`MathLibrary`で、**名前**エディット ボックス、プロジェクトの名前を指定します。

   ![MathLibrary プロジェクト](media/mathlibrary-project-name.png "MathLibrary プロジェクトの名前")

1. 選択、 **OK**を消去するボタン、**新しいプロジェクト**ダイアログと開始、 **Win32 アプリケーション ウィザード**です。

   ![Win32 アプリケーション ウィザード の概要](media/mathlibrary-project-wizard-1.png "Win32 アプリケーション ウィザード の概要")

1. **[次へ]** ボタンをクリックします。 **アプリケーション設定** ページの **アプリケーションの種類** **DLL**です。

   ![Win32 アプリケーション ウィザードで DLL を作成する](media/mathlibrary-project-wizard-2.png "Win32 アプリケーション ウィザードで DLL を作成します。")

1. **[完了]** をクリックすると、プロジェクトが作成されます。

ウィザードには、ソリューションが完了するで生成されたプロジェクトおよびソース ファイルを確認できます、**ソリューション エクスプ ローラー** Visual Studio のウィンドウ。

![Visual Studio でソリューションを生成](media/mathlibrary-solution-explorer-153.png "Visual Studio でソリューションを生成")

右側のようになりましたが、この DLL 非常にほとんど意味がありません。 DLL 関数を宣言するヘッダー ファイルを作成する次に、エクスポートすると、し、さらに実用的にする DLL に関数定義を追加します。

### <a name="to-add-a-header-file-to-the-dll"></a>ヘッダー ファイル、DLL を追加するには

1. メニュー バーで、関数のヘッダー ファイルを作成するには、選択**プロジェクト**、**新しい項目の追加**です。

1. **新しい項目の追加**ダイアログ ボックスで、左ペインで、select、 **Visual C**です。 中央のウィンドウで、 **[ヘッダー ファイル (.h)]** をクリックします。 指定`MathLibrary.h`ヘッダー ファイルの名前として。

   ![[新しい項目の追加] ダイアログ ボックスの追加ヘッダー](media/mathlibrary-add-new-item-header-file.png "[新しい項目の追加] ダイアログ ボックスのヘッダー ファイルの追加")

1. 選択、**追加**新しいエディター ウィンドウに表示される空白のヘッダー ファイルを生成するボタンをクリックします。

   ![空の MathLibrary.h ファイル エディターで](media/edit-empty-mathlibrary-header.png "エディターで空 MathLibrary.h ファイル")

1. このコードでは、ヘッダー ファイルの内容を置き換えます。

   ```cpp
   // MathLibrary.h - Contains declarations of math functions
   #pragma once

   #ifdef MATHLIBRARY_EXPORTS
   #define MATHLIBRARY_API __declspec(dllexport)
   #else
   #define MATHLIBRARY_API __declspec(dllimport)
   #endif

   // The Fibonacci recurrence relation describes a sequence F
   // where F(n) is { n = 0, a
   //               { n = 1, b
   //               { n > 1, F(n-2) + F(n-1)
   // for some initial integral values a and b.
   // If the sequence is initialized F(0) = 1, F(1) = 1,
   // then this relation produces the well-known Fibonacci
   // sequence: 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

   // Initialize a Fibonacci relation sequence
   // such that F(0) = a, F(1) = b.
   // This function must be called before any other function.
   extern "C" MATHLIBRARY_API void fibonacci_init(
       const unsigned long long a, const unsigned long long b);

   // Produce the next value in the sequence.
   // Returns true on success and updates current value and index;
   // false on overflow, leaves current value and index unchanged.
   extern "C" MATHLIBRARY_API bool fibonacci_next();

   // Get the current value in the sequence.
   extern "C" MATHLIBRARY_API unsigned long long fibonacci_current();

   // Get the position of the current value in the sequence.
   extern "C" MATHLIBRARY_API unsigned fibonacci_index();
   ```

このヘッダー ファイルでは、一般化されたフィボナッチ シーケンスでは、指定した 2 つの初期値を生成するために一部の関数を宣言します。 呼び出し`fibonacci_init(1, 1)`使い慣れたフィボナッチ数のシーケンスを生成します。

プリプロセッサ ステートメントは、ファイルの上部にあることを確認します。 既定では、dll の場合、新しいプロジェクト テンプレートが追加 ***PROJECTNAME *&#95;エクスポート**DLL プロジェクトの既定のプリプロセッサ マクロにします。 この例では、Visual Studio 定義**MATHLIBRARY&#95;エクスポート**MathLibrary DLL プロジェクトをビルドする場合。 (Visual Studio 2017 15.3 のバージョンのウィザードでは大文字に変換するには、このシンボル定義を強制しません。 プロジェクト"MathLibrary"の名前を付ける場合は、定義されたシンボル MathLibrary&#95;MATHLIBRARY ではなくエクスポート&#95;エクスポートします。 That's このシンボルを追加する上余分な手順がある理由)。

ときに、 **MATHLIBRARY&#95;エクスポート**マクロが定義されている、 **MATHLIBRARY&#95;API**マクロ セット、 `__declspec(dllexport)` 、関数宣言に修飾子です。 この修飾子は、コンパイラと他のアプリケーションで使用できるように、DLL から関数または変数をエクスポートするようにリンカーに指示します。 ときに**MATHLIBRARY&#95;エクスポート**は、たとえば、クライアント アプリケーションによって、ヘッダー ファイルが含まれている場合**MATHLIBRARY&#95;API**適用、`__declspec(dllimport)`修飾子を宣言。 この修飾子は、関数、またはアプリケーション内の変数のインポートを最適化します。 詳細については、次を参照してください。 [dllexport、dllimport](../cpp/dllexport-dllimport.md)です。

### <a name="to-add-an-implementation-to-the-dll"></a>DLL に実装を追加するには

1. エディター ウィンドウでタブを選択**MathLibrary.cpp**既に開いている場合。 以外の場合に**ソリューション エクスプ ローラー**、開かれている**MathLibrary.cpp**で、**ソースファイル**のフォルダー、 **MathLibrary**プロジェクト。

1. エディターで、MathLibrary.cpp ファイルの内容を次のコードに置き換えます。

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "stdafx.h"
   #include <utility>
   #include <limits.h>
   #include "MathLibrary.h"

   // DLL internal state variables:
   static unsigned long long previous_;  // Previous value, if any
   static unsigned long long current_;   // Current sequence value
   static unsigned index_;               // Current seq. position

   // Initialize a Fibonacci relation sequence
   // such that F(0) = a, F(1) = b.
   // This function must be called before any other function.
   void fibonacci_init(
       const unsigned long long a,
       const unsigned long long b)
   {
       index_ = 0;
       current_ = a;
       previous_ = b; // see special case when initialized
   }

   // Produce the next value in the sequence.
   // Returns true on success, false on overflow.
   bool fibonacci_next()
   {
       // check to see if we'd overflow result or position
       if ((ULLONG_MAX - previous_ < current_) ||
           (UINT_MAX == index_))
       {
           return false;
       }

       // Special case when index == 0, just return b value
       if (index_ > 0)
       {
           // otherwise, calculate next sequence value
           previous_ += current_;
       }
       std::swap(current_, previous_);
       ++index_;
       return true;
   }

   // Get the current value in the sequence.
   unsigned long long fibonacci_current()
   {
       return current_;
   }

   // Get the current index position in the sequence.
   unsigned fibonacci_index()
   {
       return index_;
   }
   ```

これまでのすべてが機能することを確認するには、ダイナミック リンク ライブラリをコンパイルします。 これをコンパイルすると、次のように選択します。**ビルド**、**ソリューションのビルド**メニュー バーでします。 出力は次のようになります。

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>stdafx.cpp
1>MathLibrary.cpp
1>dllmain.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.pdb (Partial PDB)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

以上で、Visual C を使用して DLL を作成しました。 次に、DLL のエクスポート機能を使用するクライアント アプリケーションを作成します。

## <a name="create-a-client-app-that-uses-the-dll"></a>DLL を使用するクライアント アプリケーションを作成します。

DLL を作成するときに、DLL を使用する方法を考慮する必要があります。 DLL によってエクスポートされた関数を呼び出すコードをコンパイルするには、は、クライアントのソース コードで宣言を含める必要があります。 DLL 関数にこれらの呼び出しが解決された場合、リンク時に、リンカーがいる必要があります、*インポート ライブラリ*、特別な種類の Windows の実際のコードではなく、関数を検索する方法についての情報を含むライブラリ ファイル。 実行時に、DLL をオペレーティング システムを検索する場所に、クライアントで利用できるにする必要があります。

DLL を使用するかどうか、所有または、サード パーティ製の DLL をクライアント アプリケーション プロジェクトは、DLL を宣言するヘッダーにエクスポートすると、リンカー、および DLL 自体は、インポート ライブラリを検索することである必要があります。 これを行う方法の 1 つでは、これらすべてのファイルをクライアント プロジェクトにコピーします。 クライアントは開発中に変更すると思われるサード パーティ製 dll の場合、それらを使用する最善の方法があります。 ただしもに、DLL をビルドするときに重複を避けることをお勧めします。 現在開発されている DLL ファイルのコピーを作成する場合で 1 つのコピーがない、別のヘッダー ファイルを変更または最新ライブラリを使用してしまった可能性があります。 この問題を避けるためには、DLL プロジェクトから DLL のヘッダー ファイルをインクルード クライアント プロジェクトにインクルード パスを設定することをお勧めします。 また、DLL プロジェクトから DLL インポート ライブラリをインクルードするクライアント プロジェクトにライブラリ パスを設定します。 最後に、ビルド出力ディレクトリに、DLL プロジェクトからビルドされた DLL をコピーします。 これにより、クライアント アプリ コードを使用して、同じ DLL をビルドします。

### <a name="to-create-a-client-app-in-visual-studio-2017-version-153-or-later"></a>15.3 またはそれ以降、Visual Studio 2017 年 1 バージョンでクライアント アプリを作成するには

1. 先ほど作成した、メニュー バーで、DLL を使用する C++ アプリケーションを作成するには選択**ファイル**、**新規**、**プロジェクト**です。

1. 左側のウィンドウで、**新しいプロジェクト**ダイアログで、 **Windows デスクトップ****インストール**、 **Visual C**です。 中央のウィンドウで次のように選択します。 **Windows デスクトップ ウィザード**です。 プロジェクトの名前を指定`MathClient`で、**名前**編集ボックス。

   ![クライアント プロジェクトに名前を](media/mathclient-new-project-name-153.png "クライアント プロジェクトの名前")

1. 選択**OK**を開始する、 **Windows デスクトップ プロジェクト**ウィザード。 ウィザードで、次のように選択します。 **OK**クライアント アプリのプロジェクトを作成します。

### <a name="to-create-a-client-app-in-older-versions-of-visual-studio-2017"></a>Visual Studio 2017 の旧バージョンでクライアント アプリを作成するには

1. 先ほど作成した、メニュー バーで、DLL を使用する C++ アプリケーションを作成するには選択**ファイル**、**新規**、**プロジェクト**です。

1. 左側のウィンドウで、**新しいプロジェクト**ダイアログで、 **Win32** **インストール**、**テンプレート**、 **Visual C**. 中央のウィンドウで **[Win32 コンソール アプリケーション]** をクリックします。 プロジェクトの名前を指定`MathClient`で、**名前**編集ボックス。

   ![クライアント プロジェクトに名前を](media/mathclient-project-name.png "クライアント プロジェクトの名前")

1. 選択、 **OK**を消去するボタン、**新しいプロジェクト**ダイアログと開始、 **Win32 アプリケーション ウィザード**です。 **[Win32 アプリケーション ウィザード]** ダイアログ ボックスの **[概要]** ページで、 **[次へ]** をクリックします。

1. **アプリケーション設定** ページの **アプリケーションの種類****コンソール アプリケーション**が選択されていない場合。

1. **[完了]** をクリックすると、プロジェクトが作成されます。

ウィザードが完了すると、最小限のコンソール アプリケーション プロジェクトが作成されます。 メインのソース ファイルの名前は、以前に入力したプロジェクト名と同じです。 この例では名前付き**MathClient.cpp**です。 ビルドするが、まだ、DLL は使用されません。

次に、関数を呼び出す、MathLibrary、ソース コードで、プロジェクトが MathLibrary.h ファイルを含める必要があります。 このヘッダー ファイルをクライアント アプリケーション プロジェクトにコピーし、既存の項目としてプロジェクトに追加する可能性があります。 これは、サード パーティ製のライブラリの適切な選択です。 ただし、している場合、コードで DLL の同時クライアントとして、もう一方に反映されていない 1 つのヘッダー ファイルの変更になるする可能性があります。 この問題を避けるためには、変更することができます、**追加のインクルード ディレクトリ**を元のヘッダーへのパスを含めるプロジェクト内のパス。

### <a name="to-add-the-dll-header-to-your-include-path"></a>DLL のヘッダーを追加する、パスを含める

1. 開く、**プロパティ ページ**のダイアログ ボックス、 **MathClient**プロジェクト。

1. **構成**ドロップダウン ボックスで、**すべて構成**が選択されていない場合。

1. 左のペインで選択**全般****構成プロパティ**、 **C/C++** です。

1. プロパティ ウィンドウで、ドロップダウン コントロールの横に選択、**追加のインクルード ディレクトリ**エディット ボックスをクリックして**編集**です。

   ![追加のインクルード ディレクトリ プロパティを編集](media/mathclient-additional-include-directories-property.png "追加のインクルード ディレクトリ プロパティの編集")

1. 上部ペイン内をダブルクリックして、**追加のインクルード ディレクトリ**エディット コントロールを有効にする ダイアログ ボックス。

1. エディット コントロールでの場所へのパスを指定、 **MathLibrary.h**ヘッダー ファイルです。 この場合、相対パスを使用できます。

   `..\..\MathLibrary\MathLibrary`

   ![プロパティの追加のインクルード ディレクトリ ヘッダーの場所を追加](media/mathclient-additional-include-directories.png "プロパティの追加のインクルード ディレクトリ ヘッダーの場所を追加")

1. 内のヘッダー ファイルにパスを入力すると、**追加のインクルード ディレクトリ** ダイアログ ボックスで、選択、 **OK**に戻る ボタン、**プロパティ ページ**ダイアログ ボックスと選択し、 **OK**変更を保存するボタンをクリックします。

できるようになりました、 **MathLibrary.h**ファイルし、クライアント アプリケーションで宣言して関数を使用します。 内容を置き換える**MathClient.cpp**このコードを使用しています。

```cpp
// MathClient.cpp : Client app for MathLibrary DLL.
#include "stdafx.h"
#include <iostream>
#include "MathLibrary.h"

int main()
{
    // Initialize a Fibonacci relation sequence.
    fibonacci_init(1, 1);
    // Write out the sequence values until overflow.
    do {
        std::cout << fibonacci_index() << ": "
            << fibonacci_current() << std::endl;
    } while (fibonacci_next());
    // Report count of values written before overflow.
    std::cout << fibonacci_index() + 1 <<
        " Fibonacci sequence values fit in an " <<
        "unsigned 64-bit integer." << std::endl;
}
```

このコードは、コンパイルされるもリンクされていない、リンカーがアプリをまだビルドに必要なインポート ライブラリを見つけることはできません。 リンカーは、正常にリンクする MathLibrary.lib ファイルを検索できる必要があります。 設定して、ビルドに MathLibrary.lib ファイルを追加する必要があります、**追加の依存関係**プロパティです。 もう一度、クライアント アプリケーション プロジェクトにライブラリ ファイルをコピーする可能性がありますが、もう一方に反映されていない 1 つのコピーの変更になる可能性があるライブラリと、クライアント アプリの両方が開発中にある場合は、します。 この問題を避けるためには、変更することができます、**追加のライブラリ ディレクトリ**をリンクする場合、元のライブラリへのパスを指定するプロジェクトのパス。

### <a name="to-add-the-dll-import-library-to-your-project"></a>DLL インポート ライブラリをプロジェクトに追加するには

1. 開く、**プロパティ ページ**のダイアログ ボックス、 **MathClient**プロジェクト。

1. **構成**ドロップダウン ボックスで、**すべて構成**が選択されていない場合。

1. 左のペインで選択**入力****構成プロパティ**、**リンカー**です。 プロパティ ウィンドウで、ドロップダウン コントロールの横に選択、**追加の依存関係**エディット ボックスをクリックして**編集**です。

   ![追加の依存関係プロパティを編集](media/mathclient-additional-dependencies-property.png "追加の依存関係プロパティの編集")

1. **追加の依存関係**ダイアログ ボックスで、追加`MathLibrary.lib`上部の一覧にコントロールを編集します。

   ![ライブラリ依存関係を追加](media/mathclient-additional-dependencies.png "ライブラリ依存関係の追加")

1. 選択**OK**に戻る、**プロパティ ページ** ダイアログ ボックス。

1. 左のペインで選択**全般****構成プロパティ**、**リンカー**です。 プロパティ ウィンドウで、ドロップダウン コントロールの横に選択、**追加のライブラリ ディレクトリ**エディット ボックスをクリックして**編集**です。

   ![追加のライブラリ ディレクトリ プロパティを編集](media/mathclient-additional-library-directories-property.png "追加のライブラリ ディレクトリ プロパティの編集")

1. 上部ペイン内をダブルクリックして、**追加のライブラリ ディレクトリ**エディット コントロールを有効にする ダイアログ ボックス。 エディット コントロールでの場所へのパスを指定、 **MathLibrary.lib**ファイル。 デバッグとリリースの両方に対して機能を構築するマクロを使用するには、この値を入力します。

   `..\..\MathLibrary\$(IntDir)`

   ![ライブラリ ディレクトリを追加](media/mathclient-additional-library-directories.png "ライブラリ ディレクトリを追加します。")

1. 内のライブラリ ファイルへのパスを入力すると、**追加のライブラリ ディレクトリ** ダイアログ ボックスで、選択、 **OK**に戻る ボタン、**プロパティ ページ** ダイアログ ボックス。

クライアント アプリのコンパイルして正常にリンクできますようになりましたが、まだがないを実行する必要があります。 オペレーティング システムには、アプリが読み込まれると、MathLibrary DLL を検索します。 特定のシステム ディレクトリ、環境のパス、またはローカルのアプリケーション ディレクトリに、DLL が見つからない、負荷が失敗します。 この問題を回避する方法の 1 つでは、DLL をビルド プロセスの一環として、クライアントの実行可能ファイルを格納するディレクトリにコピーします。 DLL をコピーするには、追加することができます、**ビルド後イベント**をプロジェクトにコマンドを追加するコピーする DLL のビルド出力ディレクトリにします。 ここで指定したコマンドは、がなまたはが変更されていると、マクロを使用して、構成のデバッグや量販店の正しい場所からコピーする場合にのみ、DLL をコピーします。

### <a name="to-copy-the-dll-in-a-post-build-event"></a>ビルド後のイベントの DLL をコピーするには

1. 開く、**プロパティ ページ**のダイアログ ボックス、 **MathClient**まだ開いていない場合のプロジェクトです。

1. 構成のドロップダウン ボックスで、次のように選択します。**すべて構成**が選択されていない場合。

1. 左のペインで選択**ビルド後イベント****構成プロパティ**、**ビルド イベント**です。

1. プロパティ ペインでの編集コントロールを選択、**コマンドライン**フィールド、および、このコマンドを入力します。

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![ビルド後のコマンドを追加](media/mathclient-post-build-command-line.png "ビルド後のコマンドを追加")

1. 選択、 **OK**プロジェクト プロパティに変更を保存するボタンをクリックします。

クライアント アプリがビルドおよび実行する必要があります。 選択して、アプリケーションをビルド**ビルド**、**ソリューションのビルド**メニュー バーでします。 **出力**Visual Studio のウィンドウには、次のように含める必要があります。

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>stdafx.cpp
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.pdb (Partial PDB)
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

これで、DLL で関数を呼び出すアプリケーションを作成したらです。 今すぐアプリケーションを実行しそれが何を参照してください。 メニュー バーで、次のように選択します。**デバッグ**、**デバッグなしで開始**です。 Visual Studio では、プログラムで実行するためのコマンド ウィンドウを開きます。 出力の最後の部分は、次のようになります。

![デバッグを行わない場合、クライアント アプリの起動](media/mathclient-run-without-debugging.png "デバッグを行わない場合、クライアント アプリの起動")

コマンド ウィンドウを破棄する任意のキーを押します。

DLL とクライアント アプリケーションを作成したらを試すことができます。 クライアント アプリのコードでブレークポイントを設定してみてくださいし、デバッガーでアプリを実行します。 ライブラリの呼び出しにステップ インするときの動作を参照してください。 ライブラリに他の関数を追加するか、DLL を使用する別のクライアント アプリを作成します。

アプリを展開するときにも使用して Dll を展開する必要があります。 サードパーティ製の Dll をビルドするか、含めることをアプリが使用できるようにする最も簡単な方法とも呼ばれる、アプリと同じディレクトリに挿入するには*アプリ ローカル配置*です。 展開の詳細については、次を参照してください。 [Visual c での展開](..\ide\deployment-in-visual-cpp.md)です。

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)  
[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)  
[チュートリアル: プログラムの配置 (C++)](../ide/walkthrough-deploying-your-program-cpp.md)  
[DLL 関数の Visual Basic アプリケーションからの呼び出し方](../build/calling-dll-functions-from-visual-basic-applications.md)