---
title: コンパイラの警告 (レベル 4) C4571
ms.date: 11/04/2016
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 4fe99e12c5d2dfb725e1e4aa0ac2fb0b1ccb4f28
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219886"
---
# <a name="compiler-warning-level-4-c4571"></a>コンパイラの警告 (レベル 4) C4571

情報: catch (...) の意味が Visual C++ 7.1; 以降に変更されました。構造化例外 (SEH) はキャッチされなくなりました。

C4571 は、 **/ehs**を使用してコンパイルするときに、すべての catch (...) ブロックに対して生成されます。

**/Ehs**を使用してコンパイルする場合、catch (...) ブロックは構造化例外をキャッチしません (0 による除算、null ポインターなど)。catch (...) ブロックは、明示的にスローされた C++ 例外のみをキャッチします。  詳細については、「[例外処理](../../cpp/exception-handling-in-visual-cpp.md)」を参照してください。

既定では、この警告はオフに設定されています。  この警告をオンにすると、 **/ehs**を使用してコンパイルするときに、catch (...) ブロックが構造化例外をキャッチしないようにします。  詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

C4571 は、次のいずれかの方法で解決できます。

- 引き続き catch (...) ブロックを使用して構造化例外をキャッチする場合は、 **/eha**を使用してコンパイルします。

- Catch (...) ブロックで構造化例外をキャッチしない場合でも、catch (...) ブロックを使用する場合は、C4571 を有効にしないでください。  構造化例外処理キーワード (**__try**、、および) を使用して、構造化例外をキャッチすることもでき **`__except`** **`__finally`** ます。  ただし、コンパイルされた **/ehs**デストラクターが呼び出されるのは、C++ 例外がスローされたときだけです。 SEH 例外が発生した場合は除きます。

- Catch (...) ブロックを特定の C++ 例外の catch ブロックに置き換え、必要に応じて、C++ 例外処理 (**__try**、、および) に関連する構造化例外処理を追加し **`__except`** **`__finally`** ます。  詳細については、「[構造化例外処理 (C/c + +)](../../cpp/structured-exception-handling-c-cpp.md) 」を参照してください。

詳細については、「 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C4571 が生成されます。

```cpp
// C4571.cpp
// compile with: /EHs /W4 /c
#pragma warning(default : 4571)
int main() {
   try {
      int i = 0, j = 1;
      j /= i;   // this will throw a SE (divide by zero)
   }
   catch(...) {}   // C4571 warning
}
```
