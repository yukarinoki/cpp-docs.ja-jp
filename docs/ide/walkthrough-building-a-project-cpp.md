---
title: 'チュートリアル: プロジェクトの構築 (C++) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c8d04dc3692076b867302af0e793eaac7ed25cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-building-a-project-c"></a>チュートリアル: プロジェクトの構築 (C++)
このチュートリアルでは、コードに意図的に Visual C++ 構文のエラーを挿入し、コンパイル エラーがどのように表示されるかを確認し、その修正方法について説明します。 プロジェクトをコンパイルすると、エラー メッセージによって問題の内容と発生した場所が示されます。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
-   このチュートリアルは、C++ 言語の基本を理解していることを前提としています。  
  
-   以前関連チュートリアルに記載されているが完了したことも想定[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)です。  
  
### <a name="to-fix-compilation-errors"></a>コンパイル エラーを修正するには  
  
1.  TestGames.cpp で、次のように最後の行のセミコロンを削除します。  
  
     `return 0`  
  
2.  メニュー バーの **[ビルド]**、 **[ソリューションのビルド]** の順にクリックします。  
  
3.  内のメッセージ、**エラー一覧**ウィンドウは、プロジェクトのビルドでエラーがあったことを示します。 たとえば、エラーの説明は次のようになります。  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     このエラーに関するヘルプ情報を表示することで強調表示、**エラー一覧**ウィンドウし、F1 キーを押します。  
  
4.  構文エラーのある行の最後に、セミコロンを戻します。  
  
     `return 0;`  
  
5.  メニュー バーの **[ビルド]**、 **[ソリューションのビルド]** の順にクリックします。  
  
     内のメッセージ、**出力**ウィンドウは、プロジェクトが正常にコンパイルされることを示します。  
  
    ```Output  
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------  
    1>  TestGames.cpp  
    1>  Game.vcxproj -> C:\Users\<username>\Documents\Visual Studio <version>\Projects\Game\Debug\Game.exe  
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
    ```  
  
## <a name="next-steps"></a>次の手順  
 **前:** [チュートリアル: プロジェクトとソリューション (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) &#124; **次:**[チュートリアル: プロジェクトのテスト (C++)](../ide/walkthrough-testing-a-project-cpp.md)  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)