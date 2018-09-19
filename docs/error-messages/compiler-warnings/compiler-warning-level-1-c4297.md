---
title: コンパイラの警告 (レベル 1) C4297 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4297
dev_langs:
- C++
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f615df5933cfc93918b05758f042c8cf47aa92f1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099435"
---
# <a name="compiler-warning-level-1-c4297"></a>コンパイラの警告 (レベル 1) C4297

'function': 例外をスローしないはずだがそれをする関数。

関数の宣言が含まれていますが、(恐らく暗黙的に)`noexcept`指定子、空`throw`例外指定子または[無視されます](../../cpp/nothrow-cpp.md)属性、および定義が 1 つ以上を含む[スロー。](../../cpp/try-throw-and-catch-statements-cpp.md)ステートメント。 C4297 を解決するには、`__declspec(nothrow)`、`noexcept(true)`、または `throw()` を使用して宣言した関数で例外をスローしようとしないでください。 または、`noexcept`、`throw()`、`__declspec(nothrow)` の指定を削除します。

既定では、コンパイラは、ユーザー定義のデストラクターとデアロケーターの関数およびコンパイラによって生成される特殊なメンバー関数用に、暗黙的な `noexcept(true)` 指定子を生成します。 これは、ISO C++11 標準に準拠します。 暗黙的な noexcept 指定子が生成されないようにして、コンパイラには、Visual Studio 2013 の非標準動作を元に戻すを使用して、 **/zc: implicitnoexcept-** コンパイラ オプション。 詳細については、次を参照してください。 [/Zc:implicitNoexcept (暗黙の例外指定子)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md)します。

例外の仕様の詳細については、次を参照してください。[例外の仕様 (スロー)](../../cpp/exception-specifications-throw-cpp.md)します。 またを参照してください[/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)コンパイル時の例外処理動作を変更する方法についてはします。

この警告は、_ _declspec も生成されます ([dllexport](../../cpp/dllexport-dllimport.md)) 関数が C++ 関数にある場合でも、extern"C"をマークします。

次の例では C4297 が生成されます。

```
// C4297.cpp
// compile with: /W1 /LD
void __declspec(nothrow) f1()   // declared nothrow
// try the following line instead
// void f1()
{
   throw 1;   // C4297
}
```