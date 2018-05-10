---
title: 未処理の C++ 例外 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], unhandled exceptions
- catch keyword [C++], handler not found
- exceptions [C++], unhandled
- C++ exception handling, unhandled exceptions
- unhandled exceptions [C++]
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db763ce602531b15e840013a6dd235b3fba4007e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="unhandled-c-exceptions"></a>未処理の C++ 例外
一致するハンドラーの場合 (または省略記号**キャッチ**ハンドラー)、定義済みの現在の例外に対して見つかりません`terminate`実行時に呼び出されます。 (または明示的にハンドラーのいずれかで `terminate` を呼び出すことができます)。`terminate` の既定のアクションは、`abort` を呼び出すことです。 `terminate` でアプリケーションを終了する前に他の関数を呼び出すには、呼び出す関数の名前を唯一の引数として `set_terminate` 関数を呼び出します。 `set_terminate` はプログラムの任意の時点で呼び出すことができます。 `terminate`ルーチンが常に渡す引数として指定されている最後の関数を呼び出します`set_terminate`です。  
  
## <a name="example"></a>例  
 次の例は、`char *` 例外をスローしますが、型 `char *` の例外をキャッチするハンドラーは含まれません。 `set_terminate` の呼び出しは、`terminate` に対して `term_func` を呼び出すように指示します。  
  
```  
// exceptions_Unhandled_Exceptions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void term_func() {  
   cout << "term_func was called by terminate." << endl;  
   exit( -1 );  
}  
int main() {  
   try  
   {  
      set_terminate( term_func );  
      throw "Out of memory!"; // No catch handler for this exception  
   }  
   catch( int )  
   {  
      cout << "Integer exception raised." << endl;  
   }  
   return 0;  
}  
```  
  
## <a name="output"></a>出力  
  
```  
term_func was called by terminate.  
```  
  
 `term_func` 関数は、理想的には `exit` を呼び出して、プログラムまたは現在のスレッドを終了する必要があります。 そうしないで、呼び出し元に戻った場合は、`abort` が呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [C++ 例外処理](../cpp/cpp-exception-handling.md)