---
title: コンパイラの警告 (レベル 4) C4571
description: Microsoft C++ コンパイラの警告 C4571 を文書にします。
ms.date: 08/24/2020
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 35f2b30a8ab7cfcc27ed7aae3aedd9bc81efacc8
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898554"
---
# <a name="compiler-warning-level-4-c4571"></a>コンパイラの警告 (レベル 4) C4571

> 情報: `catch(...)` Visual C++ 7.1 より後のセマンティクスが変更されました。構造化例外 (SEH) はキャッチされません

`catch(...)`コンパイラオプションを指定すると、すべてのブロックに対して C4571 が生成され **`/EHs`** ます。

## <a name="remarks"></a>注釈

コンパイラオプションを指定すると **`/EHs`** 、 `catch(...)` ブロックは構造化例外をキャッチしません。 (0 除算、または null ポインター例外など)。 `catch(...)` ブロックは明示的にスローされた C++ 例外のみをキャッチします。 詳細については、「[例外処理](../../cpp/exception-handling-in-visual-cpp.md)」を参照してください。

既定では、この警告はオフに設定されています。  ブロックでコンパイルするときに構造化例外がキャッチされないようにするには、この警告をオンにし **`/EHs`** `catch (...)` ます。 詳細については、「 [既定でオフになっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

C4571 は、次のいずれかの方法で解決できます。

- ブロックで **`/EHa`** 構造化例外をキャッチする必要がある場合は、を使用してコンパイルし `catch(...)` ます。

- ブロックで構造化例外をキャッチせずに、ブロックを使用する場合は、C4571 を有効にしない `catch(...)` で `catch(...)` ください。  構造化例外処理キーワード ( **`__try`** 、、および) を使用して、構造化例外をキャッチすることもでき **`__except`** **`__finally`** ます。  ただし、を使用してコンパイルした場合、 **`/EHs`** デストラクターは、SEH 例外が発生したときではなく、C++ 例外がスローされたときにのみ呼び出されます。

- `catch(...)`特定の c++ 例外のブロックを catch ブロックに置換します。また、必要に応じて、c++ 例外処理 ( **`__try`** 、、および) に関連する構造化例外処理を追加し **`__except`** **`__finally`** ます。   詳細については、「[構造化例外処理 (C/c + +)](../../cpp/structured-exception-handling-c-cpp.md) 」および「 [ `/EH` (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)」を参照してください。

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
