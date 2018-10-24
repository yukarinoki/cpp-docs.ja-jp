---
title: 'チュートリアル: プロジェクトのデバッグ (C++) | Microsoft Docs'
ms.custom: ''
ms.date: 09/14/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04bec9c0de7734ae2c78dd3e9c124eac3d0a55d8
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234323"
---
# <a name="walkthrough-debugging-a-project-c"></a>チュートリアル: プロジェクトのデバッグ (C++)

このチュートリアルでは、プロジェクトのテスト時に見つかった問題を修正するために、プログラムに変更を加えます。

## <a name="prerequisites"></a>必須コンポーネント

- このチュートリアルは、C++ 言語の基本を理解していることを前提としています。

- また、これまでの関連チュートリアル (「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照) を完了していることも必要です。

### <a name="to-fix-a-program-that-has-a-bug"></a>バグがあるプログラムを修正するには

1. `Cardgame` オブジェクトが破棄されるとどうなるかを確認するには、`Cardgame` クラスのデストラクターを見ます。

   メニュー バーで **[表示]** > **[クラス ビュー]** の順に選択します。

   **[クラス ビュー]** ウィンドウで、**[Game]** プロジェクト ツリーを展開し、**[Cardgame]** クラスを選択して、クラス メンバーとメソッドを表示します。

   **~Cardgame(void)** デストラクターのショートカット メニューを開き、**[定義へ移動]** を選択します。

1. Cardgame が終了したときに `totalParticipants` を減らすには、`Cardgame::~Cardgame` デストラクターの左右の中かっこの間に次のコードを入力します。

     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]

1. 変更後、Cardgame.cpp ファイルは次のコードのようになります。

     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]

1. メニュー バーで、**[ビルド]** > **[ソリューションのビルド]** の順にクリックします。

1. ビルドが完了したら、メニュー バーの **[デバッグ]** > **[デバッグ開始]** を選択するか、または **F5** キーを選択して、デバッグ モードで実行します。 プログラムは、最初のブレークポイントで停止します。

1. プログラムを実行するには、メニュー バーで **[デバッグ]** > **[ステップ オーバー]** の順に選択するか、**F10** キーを押します。

   `Cardgame` コンストラクターが実行されるたびに `totalParticipants` の値が増加します。 `PlayGames` 関数が返されると、`Cardgame` インスタンスがスコープ外に出て削除される (デストラクターが呼び出される) ため、`totalParticipants` が減少します。 `return` ステートメントが実行される直前に、`totalParticipants` は 0 になります。

1. プログラムが終了するまで続行するか、またはメニュー バーの **[デバッグ]** > **[実行]** を選択するか **F5** キーを選択して続行します。

## <a name="next-steps"></a>次の手順

**前へ:** [チュートリアル: プロジェクトのテスト (C++)](../ide/walkthrough-testing-a-project-cpp.md)<br/>
**次へ:** [チュートリアル: プログラムの配置 (C++)](../ide/walkthrough-deploying-your-program-cpp.md)<br/>

## <a name="see-also"></a>参照

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)<br/>
