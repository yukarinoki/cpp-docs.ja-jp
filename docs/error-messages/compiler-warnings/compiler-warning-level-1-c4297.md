---
title: コンパイラの警告 (レベル 1) C4297
ms.date: 11/04/2016
f1_keywords:
- C4297
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
ms.openlocfilehash: 53c9a3c311f0136136c1c57438860edcc0766e0f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220068"
---
# <a name="compiler-warning-level-1-c4297"></a>コンパイラの警告 (レベル 1) C4297

'function': 例外をスローしないはずだがそれをする関数。

関数宣言に、(場合によって **`noexcept`** は) 指定子、空の **`throw`** 例外指定子、または[__declspec (nothrow)](../../cpp/nothrow-cpp.md)属性が含まれ、定義に1つ以上の[throw](../../cpp/try-throw-and-catch-statements-cpp.md)ステートメントが含まれています。 C4297 を解決するには、`__declspec(nothrow)`、`noexcept(true)`、または `throw()` を使用して宣言した関数で例外をスローしようとしないでください。 または、、 **`noexcept`** `throw()` 、またはの仕様を削除し `__declspec(nothrow)` ます。

既定では、コンパイラは、ユーザー定義のデストラクターとデアロケーターの関数およびコンパイラによって生成される特殊なメンバー関数用に、暗黙的な `noexcept(true)` 指定子を生成します。 これは、ISO C++11 標準に準拠します。 暗黙的な noexcept 指定子が生成されないようにして、コンパイラを Visual Studio 2013 の非標準動作に戻すには、 **/zc: implicitNoexcept**オプションを使用します。 詳細については、「 [/zc: implicitNoexcept (暗黙の例外指定子)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md)」を参照してください。

例外の指定の詳細については、「[例外の指定 (throw)](../../cpp/exception-specifications-throw-cpp.md)」を参照してください。 また、コンパイル時に例外処理の動作を変更する方法の詳細については、「 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md) 」を参照してください。

この警告は、extern "C" とマークされた __declspec ([dllexport](../../cpp/dllexport-dllimport.md)) 関数に対しても生成されます。これは、C++ 関数であっても同様です。

次の例では C4297 が生成されます。

```cpp
// C4297.cpp
// compile with: /W1 /LD
void __declspec(nothrow) f1()   // declared nothrow
// try the following line instead
// void f1()
{
   throw 1;   // C4297
}
```
