---
title: 'チュートリアル: プロジェクトの構築 (C++) | Microsoft Docs'
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33332456"
---
# <a name="walkthrough-building-a-project-c"></a>チュートリアル: プロジェクトの構築 (C++)
このチュートリアルでは、コードに意図的に Visual C++ 構文のエラーを挿入し、コンパイル エラーがどのように表示されるかを確認し、その修正方法について説明します。 プロジェクトをコンパイルすると、エラー メッセージによって問題の内容と発生した場所が示されます。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
-   このチュートリアルは、C++ 言語の基本を理解していることを前提としています。  
  
-   また、これまでの関連チュートリアル (「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照) を完了していることも必要です。  
  
### <a name="to-fix-compilation-errors"></a>コンパイル エラーを修正するには  
  
1.  TestGames.cpp で、次のように最後の行のセミコロンを削除します。  
  
     `return 0`  
  
2.  メニュー バーの **[ビルド]**、 **[ソリューションのビルド]** の順にクリックします。  
  
3.  **[エラー一覧]** ウィンドウに、プロジェクトのビルド中にエラーが発生したことを示すメッセージが表示されます。 たとえば、エラーの説明は次のようになります。  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     このエラーに関するヘルプ情報を表示するには、**[エラー一覧]** ウィンドウでそのエラーを強調表示し、F1 キーを押します。  
  
4.  構文エラーのある行の最後に、セミコロンを戻します。  
  
     `return 0;`  
  
5.  メニュー バーの **[ビルド]**、 **[ソリューションのビルド]** の順にクリックします。  
  
     **[出力]** ウィンドウに、プロジェクトが正常にコンパイルされたことを示すメッセージが表示されます。  
  
    ```Output  
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------  
    1>  TestGames.cpp  
    1>  Game.vcxproj -> C:\Users\<username>\Documents\Visual Studio <version>\Projects\Game\Debug\Game.exe  
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
    ```  
  
## <a name="next-steps"></a>次の手順  
 **前へ:** [チュートリアル: プロジェクトとソリューションの使用 (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) &#124; **次へ:**[チュートリアル: プロジェクトのテスト (C++)](../ide/walkthrough-testing-a-project-cpp.md)  
  
## <a name="see-also"></a>参照  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)