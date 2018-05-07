---
title: 'チュートリアル: プロジェクトのデバッグ (C++) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: ecfda5e2549b3aa9be1f0471e301cc2a21c6fd5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-debugging-a-project-c"></a>チュートリアル: プロジェクトのデバッグ (C++)
このチュートリアルでは、プロジェクトのテスト時に検出された問題を修正するため、プログラムに変更を加えます。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
-   このチュートリアルは、C++ 言語の基本を理解していることを前提としています。  
  
-   以前関連チュートリアルに記載されているが完了したことも想定[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)です。  
  
### <a name="to-fix-a-program-that-has-a-bug"></a>バグがあるプログラムを修正するには  
  
1.  `Cardgame` オブジェクトが破棄されるとどうなるかを確認するには、`Cardgame` クラスのデストラクターを見ます。  
  
     メニュー バーで、次のように選択します。**ビュー**、**クラス ビュー**です。  
  
     **クラス ビュー**ウィンドウで、展開、**ゲーム**プロジェクト ツリーを選択、 **Cardgame**クラス メンバーとメソッドを表示するクラス。  
  
     ショートカット メニューを開き、 **~Cardgame(void)** デストラクターを選択し**定義へ移動**です。  
  
2.  Cardgame が終了したときに `totalParticipants` を減らすには、`Cardgame::~Cardgame` デストラクターの左右の中かっこの間に次のコードを入力します。  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  変更後、Cardgame.cpp ファイルは次のようになります。  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  メニュー バーの **[ビルド]**、 **[ソリューションのビルド]** の順にクリックします。  
  
5.  ビルドが完了したら、デバッグ モードで選択して実行**デバッグ**、**デバッグの開始**メニュー バーで、または F5 キーを選択します。 プログラムは、最初のブレークポイントで停止します。  
  
6.  メニュー バーで、プログラムを実行するには選択**デバッグ**、**ステップ オーバー**、または F10 キーを選択します。  
  
     Cardgame コンストラクターが実行されるたびに `totalParticipants` の値が増加します。 `PlayGames` 関数が返されると、Cardgame インスタンスがスコープ外に出て削除される (デストラクターが呼び出される) ため、`totalParticipants` が減少します。 `return` ステートメントが実行される直前に、`totalParticipants` は 0 になります。  
  
7.  セッションを終了するまで、プログラムをステップ実行を続行するかを選択して実行できるように**デバッグ**、**実行**メニュー バーで、または F5 キーを選択します。  
  
## <a name="next-steps"></a>次の手順  
 **前:** [チュートリアル: プロジェクトのテスト (C++)](../ide/walkthrough-testing-a-project-cpp.md) &#124; **次:**[チュートリアル: プログラムの配置 (C++)](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)