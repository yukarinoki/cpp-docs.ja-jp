---
title: C (構造化) と C++ 例外を混在させる |Microsoft ドキュメント
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
ms.openlocfilehash: 3e9544e10ff0af41c0ff08fa51293c67c9977f2b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420107"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (構造化) と C++ の混合例外
移植性の高いコードを記述する場合は、C++ プログラムで構造化例外処理を使用することはお勧めしません。 ただし、場合をコンパイルする **/EHa**構造化例外と C++ ソース コードを混在させるし、両方の種類の例外を処理するための機能が必要です。 C++ のコードによってスローされる例外を処理できない構造化例外ハンドラーには、オブジェクトまたは型指定された例外の概念はありません、ただし、C++**キャッチ**ハンドラーが構造化例外を処理できます。 このような C++ 例外処理の構文として (**を再試行してください**、 `throw`、**キャッチ**) C コンパイラは構造化例外処理の構文では許容されません (`__try`、 `__except`、 `__finally`)C コンパイラでサポートされています。  
  
 参照してください[_set_se_translator](../c-runtime-library/reference/set-se-translator.md) C++ 例外処理として構造化例外を処理する方法についてはします。  
  
 構造化例外と C++ 例外を混在させる場合は、次の点に注意してください。  
  
1.  C++ の例外と構造化例外を、同じ関数内で混在させることはできません。  
  
2.  例外がスローされた後のアンワインド中であっても、終了ハンドラー (`__finally` ブロック) が常に実行されます。  
  
3.  C++ 例外処理をキャッチでき、保持で、アンワインド セマンティクスでコンパイルされたすべてのモジュール、 [/EH](../build/reference/eh-exception-handling-model.md)コンパイラ オプション (このオプションにより、アンワインド セマンティクス)。  
  
4.  デストラクター関数がすべてのオブジェクトに対して呼び出されない状況もあります。 たとえば、初期化されていない関数ポインターを通じて関数呼び出しを試みているときに構造化例外が発生し、関数がその呼び出しの前に構築されたオブジェクトをパラメーターとして受け取る場合、それらのオブジェクトでスタック アンワインド中にデストラクターは呼び出されません。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [C++ プログラムでの setjmp または longjmp の使用](../cpp/using-setjmp-longjmp.md)  
  
-   [SEH と C++ EH の相違点](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>関連項目  
 [C++ 例外処理](../cpp/cpp-exception-handling.md)