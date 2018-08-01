---
title: (構造化) C と C++ 例外の混合 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e632faddb3b4f59733710a915ed121a12f4e0c6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404864"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (構造化) と C++ の混合例外
移植性の高いコードを記述する場合は、C++ プログラムで構造化例外処理を使用することはお勧めしません。 ただしを使用してコンパイルする可能性がありますも **/EHa**構造化例外と C++ のソース コードを混在させるし、両方の種類の例外を処理するためのいくつかの機能を必要しします。 C++ のコードによってスローされた例外を処理できない構造化例外ハンドラーには、オブジェクトまたは型指定された例外の概念はありません、ただし、C++**キャッチ**ハンドラーは、構造化例外を処理できます。 このような C++ 例外処理の構文として (**お試しください**、**スロー**、**キャッチ**) は受け入れられませんでしたが、C コンパイラで、構造化例外処理構文 (**_ _try**、 **_ _except**、 **_ _finally**) は、C++ コンパイラでサポートされています。  
  
 参照してください[_set_se_translator](../c-runtime-library/reference/set-se-translator.md) C++ 例外処理として構造化例外処理についてはします。  
  
 構造化例外と C++ 例外を混在させる場合は、次の点に注意してください。  
  
1.  C++ の例外と構造化例外を、同じ関数内で混在させることはできません。  
  
2.  終了ハンドラー (**_ _finally**ブロック)、例外がスローされた後のアンワインド中にも、常に実行します。  
  
3.  C++ 例外処理をキャッチできるし、保持で、アンワインド セマンティクスでコンパイルされたすべてのモジュール、 [/EH](../build/reference/eh-exception-handling-model.md)コンパイラ オプション (このオプションにより、アンワインド セマンティクス)。  
  
4.  デストラクター関数がすべてのオブジェクトに対して呼び出されない状況もあります。 たとえば、初期化されていない関数ポインターを通じて関数呼び出しを試みているときに構造化例外が発生し、関数がその呼び出しの前に構築されたオブジェクトをパラメーターとして受け取る場合、それらのオブジェクトでスタック アンワインド中にデストラクターは呼び出されません。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [C++ プログラムでの setjmp または longjmp の使用](../cpp/using-setjmp-longjmp.md)  
  
-   [SEH と C++ EH の相違点](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>関連項目  
 [C++ 例外処理](../cpp/cpp-exception-handling.md)