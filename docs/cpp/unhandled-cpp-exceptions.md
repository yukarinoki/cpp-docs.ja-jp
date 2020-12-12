---
description: 詳細については、「未処理の C++ 例外」を参照してください。
title: 未処理の C++ 例外
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], unhandled exceptions
- catch keyword [C++], handler not found
- exceptions [C++], unhandled
- C++ exception handling, unhandled exceptions
- unhandled exceptions [C++]
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
ms.openlocfilehash: 68bd8740d86df3faf4a83b7b2f269def5eeb5eca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145744"
---
# <a name="unhandled-c-exceptions"></a>未処理の C++ 例外

現在の例外に一致するハンドラー (または省略記号ハンドラー) が見つからない場合は、 **`catch`** 定義済みの `terminate` ランタイム関数が呼び出されます。 (任意のハンドラーでを明示的に呼び出すこともでき `terminate` ます)。の既定のアクションで `terminate` は、が呼び出され `abort` ます。 `terminate` でアプリケーションを終了する前に他の関数を呼び出すには、呼び出す関数の名前を唯一の引数として `set_terminate` 関数を呼び出します。 `set_terminate` はプログラムの任意の時点で呼び出すことができます。 ルーチンは、の `terminate` 引数として渡された最後の関数を常に呼び出し `set_terminate` ます。

## <a name="example"></a>例

次の例は、`char *` 例外をスローしますが、型 `char *` の例外をキャッチするハンドラーは含まれません。 `set_terminate` の呼び出しは、`terminate` に対して `term_func` を呼び出すように指示します。

```cpp
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

```Output
term_func was called by terminate.
```

`term_func` 関数は、理想的には `exit` を呼び出して、プログラムまたは現在のスレッドを終了する必要があります。 そうしないで、呼び出し元に戻った場合は、`abort` が呼び出されます。

## <a name="see-also"></a>関連項目

[例外とエラー処理に関する最新の C++ のベストプラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)
