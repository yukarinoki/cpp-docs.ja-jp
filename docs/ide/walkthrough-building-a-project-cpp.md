---
title: 'チュートリアル: プロジェクトの構築 (C++) | Microsoft Docs'
ms.custom: ''
ms.date: 09/14/2018
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
ms.openlocfilehash: eca30330e721575443ba9d3f7b0b19c315427eb2
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234126"
---
# <a name="walkthrough-building-a-project-c"></a>チュートリアル: プロジェクトの構築 (C++)

このチュートリアルでは、コードに意図的に Visual C++ 構文のエラーを挿入し、コンパイル エラーがどのように表示されるかを確認し、その修正方法について説明します。 プロジェクトをコンパイルすると、エラー メッセージによって問題の内容と発生した場所が示されます。

## <a name="prerequisites"></a>必須コンポーネント

- このチュートリアルは、C++ 言語の基本を理解していることを前提としています。

- また、これまでの関連チュートリアル (「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照) を完了していることも必要です。

### <a name="to-fix-compilation-errors"></a>コンパイル エラーを修正するには

1. Game.cpp で、次のステートメントのように最後の行のセミコロンを削除します。

    `return 0`

1. メニュー バーで、**[ビルド]** > **[ソリューションのビルド]** の順にクリックします。

1. **[エラー一覧]** ウィンドウに、プロジェクトのビルド中にエラーが発生したことを示すメッセージが表示されます。 たとえば、エラーの説明はこのエラー メッセージのようになります。

    `error C2143: syntax error: missing ';' before '}'`

  このエラーに関するヘルプ情報を表示するには、**[エラー一覧]** ウィンドウでそのエラーを強調表示し、**F1** キーを押します。

1. 構文エラーのある行の最後に、セミコロンを戻します。

     `return 0;`

1. メニュー バーで、**[ビルド]** > **[ソリューションのビルド]** の順にクリックします。

  **[出力]** ウィンドウに、プロジェクトが正常にコンパイルされたことを示すメッセージが表示されます。

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>Game.cpp
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

## <a name="next-steps"></a>次の手順

**前へ:** [チュートリアル: プロジェクトとソリューションの使用 (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)<br/>
**次へ:** [チュートリアル: プロジェクトのテスト (C++)](../ide/walkthrough-testing-a-project-cpp.md)<br/>

## <a name="see-also"></a>参照

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)<br/>
