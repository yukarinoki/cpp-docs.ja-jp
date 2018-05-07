---
title: 'チュートリアル: プロジェクトのテスト (C++) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9455fa9bf3c9f903f5018a1263978913aa35b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-testing-a-project-c"></a>チュートリアル: プロジェクトのテスト (C++)
デバッグ モードでプログラムを実行すると、ブレークポイントを使用してプログラムを停止し、変数およびオブジェクトの状態を調べることができます。  
  
 このチュートリアルでは、プログラムの実行による変数の値の変化を観察し、予測どおりの値にならない理由を推測します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
-   このチュートリアルは、C++ 言語の基本を理解していることを前提としています。  
  
-   以前関連チュートリアルに記載されているが完了したことも想定[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)です。  
  
### <a name="to-run-a-program-in-debug-mode"></a>プログラムをデバッグ モードで実行するには  
  
1.  編集する TestGames.cpp を開きます。  
  
2.  次のコード行を選択します。  
  
     `Cardgame.solitaire(1);`  
  
3.  メニュー バーで、その行にブレークポイントを設定するには選択**デバッグ**、**ブレークポイントの切り替え**、か、F9 キーを選択します。 赤い円が行の左側に表示されて、その行にブレークポイントが設定されていることを示します。 ブレークポイントを削除するには、もう一度メニュー コマンドを選択するか F9 キーを押します。  
  
     マウスを使用している場合は、左の余白をクリックすることでブレークポイントを設定/解除できます。  
  
4.  メニュー バーで、次のように選択します。**デバッグ**、**デバッグの開始**、または、F5 キーを選択します。  
  
     プログラムがブレークポイントの行に到達すると、実行が一時的に停止されます。プログラムが中断モードであるためです。 コード行の左側の黄色の矢印は、次に実行される行を示します。  
  
5.  `Cardgame::totalParticipants` 変数の値を調べるには、ポインターを `Cardgame` に移動し、ヒント ウィンドウの左側にある展開コントロールに移動します。 変数の名前 "`totalParticipants`" とその値 "12" が表示されます。  
  
     ショートカット メニューを開き、`Cardgame::totalParticipants`変数を選択し**ウォッチ式の追加**でその変数を表示する、**ウォッチ 1**ウィンドウです。 また、変数を選択し、ドラッグすることができます、**ウォッチ 1**ウィンドウです。  
  
6.  メニュー バーで、コードの次の行にステップ インするには選択**デバッグ**、**ステップ オーバー**、または F10 キーを選択します。  
  
     値`Cardgame::totalParticipants`で、**ウォッチ 1** 13 とウィンドウが表示されます。  
  
7.  ショートカット メニューを開き、`return 0;`ステートメントを選択し**カーソルまで実行**です。 コード左側の黄色の矢印は、次に実行されるステートメントを示します。  
  
8.  `Cardgame::totalParticipants` の値は Cardgame が終了すると減ります。 この時点では、`Cardgame::totalParticipants`すべての Cardgame インスタンスが削除されているために、0 を等しく必要がありますが、**ウォッチ 1**ウィンドウには、ことを示します`Cardgame::totalparticipants`"18"と等しい。 これは、検出し、次のチュートリアルを完了して修正することができます、コードにバグがあることを示します[チュートリアル: プロジェクト (C++) をデバッグ](../ide/walkthrough-debugging-a-project-cpp.md)です。  
  
9. 中止するには、メニュー バーで、次のように選択します。**デバッグ**、**デバッグの停止**、か、shift + f5 キーボード ショートカットを選択します。  
  
## <a name="next-steps"></a>次の手順  
 **前:** [チュートリアル: プロジェクトの構築 (C++)](../ide/walkthrough-building-a-project-cpp.md) &#124; **次:**[チュートリアル: プロジェクトのデバッグ (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)