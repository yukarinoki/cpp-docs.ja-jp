---
title: Visual C での例外処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0acd5df644f097d19e5f9708f0a059a31f3e9ee9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413324"
---
# <a name="exception-handling-in-visual-c"></a>Visual C++ での例外処理
例外とは、プログラムが通常の実行パスに沿って進むことを妨げるエラー状態のことであり、プログラムで制御できない可能性があります。 オブジェクトの作成、ファイルの入出力、および他のモジュールから行われる関数呼び出しを含む特定のアクションは、プログラムが正しく実行されている場合でも、すべて例外の潜在的な原因となります。 堅牢なコードは例外を予期し、それを処理します。  
  
 1 つのプログラムまたはモジュール内の論理エラーを検出するには、例外ではなくアサーションを使用して (を参照してください[を使用してアサーション](/visualstudio/debugger/c-cpp-assertions))。  
  
 Visual C++ は、3 種類の例外処理をサポートしています。  
  
-   [C++ 例外処理](../cpp/cpp-exception-handling.md)  
  
     ほとんどの C++ プログラムでは、タイプ セーフでオブジェクトのデストラクターがスタック アンワインド中に確実に呼び出されるようにする、C++ 例外処理を使用する必要があります。  
  
-   [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)  
  
     Windows には、SEH と呼ばれる独自の例外機構が備わっています。 これは C++ または MFC プログラミングには推奨されません。 非 MFC C プログラムでのみ、SEH を使用します。  
  
-   [MFC 例外](../mfc/exception-handling-in-mfc.md)  
  
     MFC はバージョン 3.0 以降、C++ 例外を使用していますが、フォームの C++ 例外に似た古い例外処理マクロを引き続きサポートします。 これらのマクロは新しいプログラミングで推奨されませんが、下位互換性のために引き続きサポートされます。 既にマクロを使用しているプログラムでは、自由に C++ の例外も使用できます。 プリプロセス時に、Visual C++ Version 2.0 時点では、マクロは C++ 言語の Visual C++ の実装で定義されている例外処理キーワードに評価されます。 C++ 例外処理の使用を開始するときは、既存の例外処理マクロをそのまま維持できます。  
  
 使用して、 [/EH](../build/reference/eh-exception-handling-model.md) ; のプロジェクトで使用する例外処理の種類を指定するコンパイラ オプションC++ 例外処理では、既定値です。 エラー処理機構を併用しないでください。たとえば、構造化例外処理で C++ 例外を使用しないでください。 C++ 例外処理を使用すると、コードの移植性が高くなり、すべての種類の例外を処理できるようになります。 構造化例外処理の欠点の詳細については、次を参照してください。[構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)です。 MFC マクロと C++ 例外を混在させるアドバイスは、次を参照してください。[例外: MFC マクロと C++ 例外](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)です。  
  
 CLR アプリケーションで例外を処理する方法については、次を参照してください。[例外処理](../windows/exception-handling-cpp-component-extensions.md)です。  
  
 X64 で処理する例外については、プロセッサを参照してください[例外処理 (x64)](../build/exception-handling-x64.md)です。  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)